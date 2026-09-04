# Intifact\Sdk\PublicApi

Endpoints públicos sin auth (consulta de comprobantes por clientes finales)

All URIs are relative to http://localhost:3000, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**apiV1PublicConsultarRucTipoDocSerieNumeroGet()**](PublicApi.md#apiV1PublicConsultarRucTipoDocSerieNumeroGet) | **GET** /api/v1/public/consultar/{ruc}/{tipoDoc}/{serie}/{numero} | Consultar un comprobante (público, sin auth) |
| [**apiV1PublicConsultarRucTipoDocSerieNumeroPdfGet()**](PublicApi.md#apiV1PublicConsultarRucTipoDocSerieNumeroPdfGet) | **GET** /api/v1/public/consultar/{ruc}/{tipoDoc}/{serie}/{numero}/pdf | Descargar PDF del comprobante (público) |
| [**apiV1PublicConsultarRucTipoDocSerieNumeroXmlGet()**](PublicApi.md#apiV1PublicConsultarRucTipoDocSerieNumeroXmlGet) | **GET** /api/v1/public/consultar/{ruc}/{tipoDoc}/{serie}/{numero}/xml | Descargar XML firmado (público) |


## `apiV1PublicConsultarRucTipoDocSerieNumeroGet()`

```php
apiV1PublicConsultarRucTipoDocSerieNumeroGet($ruc, $tipo_doc, $serie, $numero, $total, $fecha, $receptor)
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
    $apiInstance->apiV1PublicConsultarRucTipoDocSerieNumeroGet($ruc, $tipo_doc, $serie, $numero, $total, $fecha, $receptor);
} catch (Exception $e) {
    echo 'Exception when calling PublicApi->apiV1PublicConsultarRucTipoDocSerieNumeroGet: ', $e->getMessage(), PHP_EOL;
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

## `apiV1PublicConsultarRucTipoDocSerieNumeroPdfGet()`

```php
apiV1PublicConsultarRucTipoDocSerieNumeroPdfGet($ruc, $tipo_doc, $serie, $numero)
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

try {
    $apiInstance->apiV1PublicConsultarRucTipoDocSerieNumeroPdfGet($ruc, $tipo_doc, $serie, $numero);
} catch (Exception $e) {
    echo 'Exception when calling PublicApi->apiV1PublicConsultarRucTipoDocSerieNumeroPdfGet: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **ruc** | **string**|  | |
| **tipo_doc** | **string**|  | |
| **serie** | **string**|  | |
| **numero** | **string**|  | |

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

## `apiV1PublicConsultarRucTipoDocSerieNumeroXmlGet()`

```php
apiV1PublicConsultarRucTipoDocSerieNumeroXmlGet($ruc, $tipo_doc, $serie, $numero)
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

try {
    $apiInstance->apiV1PublicConsultarRucTipoDocSerieNumeroXmlGet($ruc, $tipo_doc, $serie, $numero);
} catch (Exception $e) {
    echo 'Exception when calling PublicApi->apiV1PublicConsultarRucTipoDocSerieNumeroXmlGet: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **ruc** | **string**|  | |
| **tipo_doc** | **string**|  | |
| **serie** | **string**|  | |
| **numero** | **string**|  | |

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
