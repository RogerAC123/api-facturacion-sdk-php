# intifact/sdk (PHP)

SDK PHP para la **API de Facturación Electrónica SUNAT de Intifact** (Perú),
generado con [OpenAPI Generator](https://openapi-generator.tech) desde el spec
que la API expone en `/docs/json`. Facturas, boletas, notas de crédito/débito,
guías de remisión (remitente y transportista), resúmenes diarios y
comunicaciones de baja.

## Requisitos

- PHP 8.1+
- Extensiones `curl`, `json`, `mbstring` (vienen habilitadas por defecto en la
  mayoría de instalaciones)

## Instalación

```bash
composer require intifact/sdk
```

## Autenticación

La API no está modelada con un `securityScheme` de OpenAPI (el chequeo de API
key vive en un plugin de Fastify), así que el header se agrega directo en el
cliente Guzzle que se le pasa al SDK:

```php
<?php
require_once __DIR__ . '/vendor/autoload.php';

$config = Intifact\Sdk\Configuration::getDefaultConfiguration()
    ->setHost('https://api-facturacion.intifact.com');

$httpClient = new GuzzleHttp\Client([
    'headers' => ['Authorization' => 'Bearer ' . getenv('FACTURACION_API_KEY')],
]);
```

## Uso básico — enviar una factura

```php
<?php
require_once __DIR__ . '/vendor/autoload.php';

use Intifact\Sdk\Configuration;
use Intifact\Sdk\ApiException;
use Intifact\Sdk\Api\InvoiceApi;
use Intifact\Sdk\Model\ApiV1InvoiceSendPostRequest;
use Intifact\Sdk\Model\ApiV1InvoiceSendPostRequestDetalleInner;

$config = Configuration::getDefaultConfiguration()
    ->setHost('https://api-facturacion.intifact.com');

$httpClient = new GuzzleHttp\Client([
    'headers' => ['Authorization' => 'Bearer ' . getenv('FACTURACION_API_KEY')],
]);

$invoiceApi = new InvoiceApi($httpClient, $config);

$item = new ApiV1InvoiceSendPostRequestDetalleInner([
    'unidad' => 'NIU',
    'cantidad' => 2,
    'cod_producto' => 'PROD001',
    'descripcion' => 'Laptop HP 15',
    'monto_valor_unitario' => 2500.00,
    'monto_base_igv' => 5000.00,
    'porcentaje_igv' => 18,
    'igv' => 900.00,
    'tip_afe_igv' => '10',
    'total_impuestos' => 900.00,
    'monto_precio_unitario' => 2950.00,
    'monto_valor_venta' => 5000.00,
    // Código de Producto SUNAT (UNSPSC) — SUNAT lo exige desde 2027-01-01
    // para determinados bienes (error 3496 si falta o es inválido).
    'cod_prod_sunat' => '43211508',
]);

$body = new ApiV1InvoiceSendPostRequest([
    'empresa_ruc' => '20553510661',
    'tipo_doc' => '01',
    'serie' => 'F001',
    'correlativo' => '100',
    'tipo_moneda' => 'PEN',
    'fecha_emision' => '2026-01-15',
    'tipo_operacion' => '0101',
    'cliente_tipo_doc' => '6',
    'cliente_num_doc' => '20000000001',
    'cliente_razon_social' => 'EMPRESA CLIENTE SAC',
    'detalle' => [$item],
    // ...monto_oper_gravadas, monto_igv, sub_total, leyendas, forma_pago, etc.
]);

try {
    $resp = $invoiceApi->apiV1InvoiceSendPost($body);
    // 202 — el documento queda ENCOLADO, SUNAT lo procesa en background
    echo 'Encolado: ' . $resp->getData()->getId() . "\n";
} catch (ApiException $e) {
    // El body real del error (400/401/409/...) viene en getResponseBody()
    echo 'Error ' . $e->getCode() . ': ' . $e->getResponseBody() . "\n";
}
```

Nota: los arrays de construcción usan claves `snake_case` (`cod_producto`)
aunque el JSON que viaja por HTTP sigue siendo `camelCase` (`codProducto`) —
el modelo hace la conversión automáticamente.

## Manejo de errores

Toda respuesta fuera de 2xx llega como `Intifact\Sdk\ApiException` (no como
excepción genérica de red): `getCode()` trae el status HTTP y
`getResponseBody()` el JSON crudo `{ success: false, message, errors? }` que
devuelve la API.

```php
try {
    $invoiceApi->apiV1InvoiceSendPost($body);
} catch (ApiException $e) {
    if ($e->getCode() === 409) {
        // Comprobante ya en proceso — NO reintentar con otro correlativo,
        // esperar el resultado. Ver /documents/{id} para el estado final.
    }
}
```

## APIs disponibles

| Clase | Para qué |
|---|---|
| `InvoiceApi` | Facturas/boletas: enviar, PDF, XML, CDR |
| `NoteApi` | Notas de crédito/débito |
| `DespatchApi` | Guías de remisión (remitente y transportista) |
| `SummaryApi` | Resumen diario y comunicación de baja |
| `DocumentsApi` | Listar/consultar documentos, reintentar fallidos |
| `QueuesApi` | Estado de las colas BullMQ |
| `CompanyApi` / `BranchesApi` | Empresas y establecimientos (solo lectura) |
| `WebhooksApi` | Suscripciones y entregas de webhooks |
| `PlansApi` | Planes y consumo (quota) |
| `PublicApi` | Consulta pública de comprobantes (sin auth) |
| `AuthApi` | Autenticación |
| `SystemApi` | `/health`, catálogos SUNAT |

## Regenerar desde la API

El proyecto se generó con [OpenAPI Generator](https://openapi-generator.tech)
(`php`) contra `https://api-facturacion.intifact.com/docs/json`. Para
regenerar tras un cambio de la API:

```bash
npx @openapitools/openapi-generator-cli generate \
  -i https://api-facturacion.intifact.com/docs/json \
  -g php --invoker-package "Intifact\Sdk" \
  --additional-properties=composerVendorName=intifact,composerProjectName=sdk \
  -o .
```

## Nota sobre los nombres de métodos

Las rutas de la API no declaran `operationId` explícito en su schema de
Fastify, así que el generador deriva nombres desde el método+path
(`apiV1InvoiceSendPost` en vez de algo como `sendInvoice`). Si la API le
agrega `operationId` a sus rutas, una regeneración futura produciría nombres
más limpios sin romper compatibilidad de comportamiento.
