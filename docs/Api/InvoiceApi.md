# Intifact\Sdk\InvoiceApi

Facturas y Boletas (01, 03)

All URIs are relative to http://localhost:3099, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**computeInvoice()**](InvoiceApi.md#computeInvoice) | **POST** /api/v1/invoice/compute | Calcular importes (IGV, descuentos, totales) sin emitir |
| [**getInvoiceCdr()**](InvoiceApi.md#getInvoiceCdr) | **GET** /api/v1/invoice/{id}/cdr | Descargar CDR (constancia de SUNAT) |
| [**getInvoicePdf()**](InvoiceApi.md#getInvoicePdf) | **GET** /api/v1/invoice/{id}/pdf | Obtener PDF (A4 oficina, ticket 80mm o ticket 58mm POS) |
| [**getInvoiceXml()**](InvoiceApi.md#getInvoiceXml) | **GET** /api/v1/invoice/{id}/xml | Descargar XML firmado |
| [**sendInvoice()**](InvoiceApi.md#sendInvoice) | **POST** /api/v1/invoice/send | Enviar factura (01) o boleta (03) a SUNAT |


## `computeInvoice()`

```php
computeInvoice($compute_invoice_request): \Intifact\Sdk\Model\ComputeInvoice200Response
```

Calcular importes (IGV, descuentos, totales) sin emitir

Motor de cálculo: recibe ítems crudos (cantidad, valorUnitario sin IGV, afectación, descuento) y un descuento global opcional, y devuelve TODOS los importes fiscales calculados (bases, IGV, descuentos, totales, monto en letras). No emite ni persiste nada — úsalo para previsualizar o para alimentar POST /invoice/send.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: apiKey
$config = Intifact\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Intifact\Sdk\Api\InvoiceApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$compute_invoice_request = new \Intifact\Sdk\Model\ComputeInvoiceRequest(); // \Intifact\Sdk\Model\ComputeInvoiceRequest

try {
    $result = $apiInstance->computeInvoice($compute_invoice_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling InvoiceApi->computeInvoice: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **compute_invoice_request** | [**\Intifact\Sdk\Model\ComputeInvoiceRequest**](../Model/ComputeInvoiceRequest.md)|  | |

### Return type

[**\Intifact\Sdk\Model\ComputeInvoice200Response**](../Model/ComputeInvoice200Response.md)

### Authorization

[apiKey](../../README.md#apiKey)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getInvoiceCdr()`

```php
getInvoiceCdr($id)
```

Descargar CDR (constancia de SUNAT)

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: apiKey
$config = Intifact\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Intifact\Sdk\Api\InvoiceApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string

try {
    $apiInstance->getInvoiceCdr($id);
} catch (Exception $e) {
    echo 'Exception when calling InvoiceApi->getInvoiceCdr: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**|  | |

### Return type

void (empty response body)

### Authorization

[apiKey](../../README.md#apiKey)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getInvoicePdf()`

```php
getInvoicePdf($id, $format)
```

Obtener PDF (A4 oficina, ticket 80mm o ticket 58mm POS)

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: apiKey
$config = Intifact\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Intifact\Sdk\Api\InvoiceApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string
$format = 'a4'; // string

try {
    $apiInstance->getInvoicePdf($id, $format);
} catch (Exception $e) {
    echo 'Exception when calling InvoiceApi->getInvoicePdf: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**|  | |
| **format** | **string**|  | [optional] [default to &#39;a4&#39;] |

### Return type

void (empty response body)

### Authorization

[apiKey](../../README.md#apiKey)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getInvoiceXml()`

```php
getInvoiceXml($id)
```

Descargar XML firmado

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: apiKey
$config = Intifact\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Intifact\Sdk\Api\InvoiceApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string

try {
    $apiInstance->getInvoiceXml($id);
} catch (Exception $e) {
    echo 'Exception when calling InvoiceApi->getInvoiceXml: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**|  | |

### Return type

void (empty response body)

### Authorization

[apiKey](../../README.md#apiKey)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `sendInvoice()`

```php
sendInvoice($send_invoice_request): \Intifact\Sdk\Model\SendInvoice202Response
```

Enviar factura (01) o boleta (03) a SUNAT

Genera el XML UBL 2.1, lo firma digitalmente y lo encola para envío asíncrono a SUNAT. Responde 202 inmediatamente. Para conocer el resultado final consultar GET /documents/{id}. Idempotente por (RUC emisor, tipoDoc, serie, correlativo): reenviar el mismo comprobante NO lo duplica. Si ya fue aceptado devuelve el mismo id y hash sin reenviar nada a SUNAT; si sigue en proceso responde 409 (esperá el resultado, no cambies el correlativo). Solo un RECHAZADO exige un correlativo nuevo.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: apiKey
$config = Intifact\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Intifact\Sdk\Api\InvoiceApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$send_invoice_request = new \Intifact\Sdk\Model\SendInvoiceRequest(); // \Intifact\Sdk\Model\SendInvoiceRequest

try {
    $result = $apiInstance->sendInvoice($send_invoice_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling InvoiceApi->sendInvoice: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **send_invoice_request** | [**\Intifact\Sdk\Model\SendInvoiceRequest**](../Model/SendInvoiceRequest.md)|  | |

### Return type

[**\Intifact\Sdk\Model\SendInvoice202Response**](../Model/SendInvoice202Response.md)

### Authorization

[apiKey](../../README.md#apiKey)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
