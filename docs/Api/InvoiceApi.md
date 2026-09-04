# Intifact\Sdk\InvoiceApi

Facturas y Boletas (01, 03)

All URIs are relative to http://localhost:3000, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**apiV1InvoiceComputePost()**](InvoiceApi.md#apiV1InvoiceComputePost) | **POST** /api/v1/invoice/compute | Calcular importes (IGV, descuentos, totales) sin emitir |
| [**apiV1InvoiceIdCdrGet()**](InvoiceApi.md#apiV1InvoiceIdCdrGet) | **GET** /api/v1/invoice/{id}/cdr | Descargar CDR (constancia de SUNAT) |
| [**apiV1InvoiceIdPdfGet()**](InvoiceApi.md#apiV1InvoiceIdPdfGet) | **GET** /api/v1/invoice/{id}/pdf | Obtener PDF (A4 oficina, ticket 80mm o ticket 58mm POS) |
| [**apiV1InvoiceIdXmlGet()**](InvoiceApi.md#apiV1InvoiceIdXmlGet) | **GET** /api/v1/invoice/{id}/xml | Descargar XML firmado |
| [**apiV1InvoiceSendPost()**](InvoiceApi.md#apiV1InvoiceSendPost) | **POST** /api/v1/invoice/send | Enviar factura (01) o boleta (03) a SUNAT |


## `apiV1InvoiceComputePost()`

```php
apiV1InvoiceComputePost($api_v1_invoice_compute_post_request): \Intifact\Sdk\Model\ApiV1InvoiceComputePost200Response
```

Calcular importes (IGV, descuentos, totales) sin emitir

Motor de cálculo: recibe ítems crudos (cantidad, valorUnitario sin IGV, afectación, descuento) y un descuento global opcional, y devuelve TODOS los importes fiscales calculados (bases, IGV, descuentos, totales, monto en letras). No emite ni persiste nada — úsalo para previsualizar o para alimentar POST /invoice/send.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new Intifact\Sdk\Api\InvoiceApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$api_v1_invoice_compute_post_request = new \Intifact\Sdk\Model\ApiV1InvoiceComputePostRequest(); // \Intifact\Sdk\Model\ApiV1InvoiceComputePostRequest

try {
    $result = $apiInstance->apiV1InvoiceComputePost($api_v1_invoice_compute_post_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling InvoiceApi->apiV1InvoiceComputePost: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **api_v1_invoice_compute_post_request** | [**\Intifact\Sdk\Model\ApiV1InvoiceComputePostRequest**](../Model/ApiV1InvoiceComputePostRequest.md)|  | |

### Return type

[**\Intifact\Sdk\Model\ApiV1InvoiceComputePost200Response**](../Model/ApiV1InvoiceComputePost200Response.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `apiV1InvoiceIdCdrGet()`

```php
apiV1InvoiceIdCdrGet($id)
```

Descargar CDR (constancia de SUNAT)

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new Intifact\Sdk\Api\InvoiceApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$id = 'id_example'; // string

try {
    $apiInstance->apiV1InvoiceIdCdrGet($id);
} catch (Exception $e) {
    echo 'Exception when calling InvoiceApi->apiV1InvoiceIdCdrGet: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**|  | |

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

## `apiV1InvoiceIdPdfGet()`

```php
apiV1InvoiceIdPdfGet($id, $format)
```

Obtener PDF (A4 oficina, ticket 80mm o ticket 58mm POS)

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new Intifact\Sdk\Api\InvoiceApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$id = 'id_example'; // string
$format = 'a4'; // string

try {
    $apiInstance->apiV1InvoiceIdPdfGet($id, $format);
} catch (Exception $e) {
    echo 'Exception when calling InvoiceApi->apiV1InvoiceIdPdfGet: ', $e->getMessage(), PHP_EOL;
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

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: Not defined

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `apiV1InvoiceIdXmlGet()`

```php
apiV1InvoiceIdXmlGet($id)
```

Descargar XML firmado

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new Intifact\Sdk\Api\InvoiceApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$id = 'id_example'; // string

try {
    $apiInstance->apiV1InvoiceIdXmlGet($id);
} catch (Exception $e) {
    echo 'Exception when calling InvoiceApi->apiV1InvoiceIdXmlGet: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**|  | |

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

## `apiV1InvoiceSendPost()`

```php
apiV1InvoiceSendPost($api_v1_invoice_send_post_request): \Intifact\Sdk\Model\ApiV1InvoiceSendPost202Response
```

Enviar factura (01) o boleta (03) a SUNAT

Genera el XML UBL 2.1, lo firma digitalmente y lo encola para envío asíncrono a SUNAT. Responde 202 inmediatamente. Para conocer el resultado final consultar GET /documents/{id}. Idempotente por (RUC emisor, tipoDoc, serie, correlativo): reenviar el mismo comprobante NO lo duplica. Si ya fue aceptado devuelve el mismo id y hash sin reenviar nada a SUNAT; si sigue en proceso responde 409 (esperá el resultado, no cambies el correlativo). Solo un RECHAZADO exige un correlativo nuevo.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new Intifact\Sdk\Api\InvoiceApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$api_v1_invoice_send_post_request = new \Intifact\Sdk\Model\ApiV1InvoiceSendPostRequest(); // \Intifact\Sdk\Model\ApiV1InvoiceSendPostRequest

try {
    $result = $apiInstance->apiV1InvoiceSendPost($api_v1_invoice_send_post_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling InvoiceApi->apiV1InvoiceSendPost: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **api_v1_invoice_send_post_request** | [**\Intifact\Sdk\Model\ApiV1InvoiceSendPostRequest**](../Model/ApiV1InvoiceSendPostRequest.md)|  | |

### Return type

[**\Intifact\Sdk\Model\ApiV1InvoiceSendPost202Response**](../Model/ApiV1InvoiceSendPost202Response.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
