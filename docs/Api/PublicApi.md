# Intifact\Sdk\PublicApi

Endpoints públicos sin auth (consulta de comprobantes por clientes finales)

All URIs are relative to http://localhost:3099, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**consultarComprobante()**](PublicApi.md#consultarComprobante) | **GET** /api/v1/public/consultar/{ruc}/{tipoDoc}/{serie}/{numero} | Consultar un comprobante (público, sin auth) |
| [**consultarComprobantePdf()**](PublicApi.md#consultarComprobantePdf) | **GET** /api/v1/public/consultar/{ruc}/{tipoDoc}/{serie}/{numero}/pdf | Descargar PDF del comprobante (público) |
| [**consultarComprobanteXml()**](PublicApi.md#consultarComprobanteXml) | **GET** /api/v1/public/consultar/{ruc}/{tipoDoc}/{serie}/{numero}/xml | Descargar XML firmado (público) |


## `consultarComprobante()`

```php
consultarComprobante($ruc, $tipo_doc, $serie, $numero, $total, $fecha, $receptor)
```

Consultar un comprobante (público, sin auth)

Verificación pública de un comprobante emitido. Retorna datos mínimos no sensibles. El parámetro `total` es opcional pero recomendado como anti-scraping (debe coincidir con el monto total).

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new Intifact\Sdk\Api\PublicApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$ruc = 'ruc_example'; // string
$tipo_doc = 'tipo_doc_example'; // string
$serie = 'serie_example'; // string
$numero = 'numero_example'; // string
$total = 3.4; // float
$fecha = 'fecha_example'; // string
$receptor = 'receptor_example'; // string

try {
    $apiInstance->consultarComprobante($ruc, $tipo_doc, $serie, $numero, $total, $fecha, $receptor);
} catch (Exception $e) {
    echo 'Exception when calling PublicApi->consultarComprobante: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **ruc** | **string**|  | |
| **tipo_doc** | **string**|  | |
| **serie** | **string**|  | |
| **numero** | **string**|  | |
| **total** | **float**|  | [optional] |
| **fecha** | **string**|  | [optional] |
| **receptor** | **string**|  | [optional] |

### Return type

void (empty response body)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: Not defined

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `consultarComprobantePdf()`

```php
consultarComprobantePdf($ruc, $tipo_doc, $serie, $numero, $total, $fecha, $receptor)
```

Descargar PDF del comprobante (público)

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new Intifact\Sdk\Api\PublicApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$ruc = 'ruc_example'; // string
$tipo_doc = 'tipo_doc_example'; // string
$serie = 'serie_example'; // string
$numero = 'numero_example'; // string
$total = 3.4; // float
$fecha = 'fecha_example'; // string
$receptor = 'receptor_example'; // string

try {
    $apiInstance->consultarComprobantePdf($ruc, $tipo_doc, $serie, $numero, $total, $fecha, $receptor);
} catch (Exception $e) {
    echo 'Exception when calling PublicApi->consultarComprobantePdf: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **ruc** | **string**|  | |
| **tipo_doc** | **string**|  | |
| **serie** | **string**|  | |
| **numero** | **string**|  | |
| **total** | **float**|  | [optional] |
| **fecha** | **string**|  | [optional] |
| **receptor** | **string**|  | [optional] |

### Return type

void (empty response body)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: Not defined

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `consultarComprobanteXml()`

```php
consultarComprobanteXml($ruc, $tipo_doc, $serie, $numero, $total, $fecha, $receptor)
```

Descargar XML firmado (público)

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new Intifact\Sdk\Api\PublicApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$ruc = 'ruc_example'; // string
$tipo_doc = 'tipo_doc_example'; // string
$serie = 'serie_example'; // string
$numero = 'numero_example'; // string
$total = 3.4; // float
$fecha = 'fecha_example'; // string
$receptor = 'receptor_example'; // string

try {
    $apiInstance->consultarComprobanteXml($ruc, $tipo_doc, $serie, $numero, $total, $fecha, $receptor);
} catch (Exception $e) {
    echo 'Exception when calling PublicApi->consultarComprobanteXml: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **ruc** | **string**|  | |
| **tipo_doc** | **string**|  | |
| **serie** | **string**|  | |
| **numero** | **string**|  | |
| **total** | **float**|  | [optional] |
| **fecha** | **string**|  | [optional] |
| **receptor** | **string**|  | [optional] |

### Return type

void (empty response body)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: Not defined

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
