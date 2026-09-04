# Intifact\Sdk\NoteApi

Notas de Crédito/Débito (07, 08)

All URIs are relative to http://localhost:3000, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**apiV1NoteComputePost()**](NoteApi.md#apiV1NoteComputePost) | **POST** /api/v1/note/compute | Calcular importes (IGV, descuentos, totales) sin emitir |
| [**apiV1NoteIdCdrGet()**](NoteApi.md#apiV1NoteIdCdrGet) | **GET** /api/v1/note/{id}/cdr | Descargar CDR (constancia de SUNAT) |
| [**apiV1NoteIdPdfGet()**](NoteApi.md#apiV1NoteIdPdfGet) | **GET** /api/v1/note/{id}/pdf | Obtener PDF de la nota |
| [**apiV1NoteIdXmlGet()**](NoteApi.md#apiV1NoteIdXmlGet) | **GET** /api/v1/note/{id}/xml | Descargar XML firmado |
| [**apiV1NoteSendPost()**](NoteApi.md#apiV1NoteSendPost) | **POST** /api/v1/note/send | Enviar nota de crédito (07) o débito (08) a SUNAT |


## `apiV1NoteComputePost()`

```php
apiV1NoteComputePost($api_v1_note_compute_post_request): \Intifact\Sdk\Model\ApiV1InvoiceComputePost200Response
```

Calcular importes (IGV, descuentos, totales) sin emitir

Motor de cálculo para notas: recibe ítems crudos (cantidad, valorUnitario sin IGV, afectación, descuento) y un descuento global opcional, y devuelve TODOS los importes fiscales calculados. No emite ni persiste nada — úsalo para previsualizar o para alimentar POST /note/send (agrega tú el documento afectado y el motivo).

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new Intifact\Sdk\Api\NoteApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$api_v1_note_compute_post_request = new \Intifact\Sdk\Model\ApiV1NoteComputePostRequest(); // \Intifact\Sdk\Model\ApiV1NoteComputePostRequest

try {
    $result = $apiInstance->apiV1NoteComputePost($api_v1_note_compute_post_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling NoteApi->apiV1NoteComputePost: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **api_v1_note_compute_post_request** | [**\Intifact\Sdk\Model\ApiV1NoteComputePostRequest**](../Model/ApiV1NoteComputePostRequest.md)|  | |

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

## `apiV1NoteIdCdrGet()`

```php
apiV1NoteIdCdrGet($id)
```

Descargar CDR (constancia de SUNAT)

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new Intifact\Sdk\Api\NoteApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$id = 'id_example'; // string

try {
    $apiInstance->apiV1NoteIdCdrGet($id);
} catch (Exception $e) {
    echo 'Exception when calling NoteApi->apiV1NoteIdCdrGet: ', $e->getMessage(), PHP_EOL;
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

## `apiV1NoteIdPdfGet()`

```php
apiV1NoteIdPdfGet($id)
```

Obtener PDF de la nota

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new Intifact\Sdk\Api\NoteApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$id = 'id_example'; // string

try {
    $apiInstance->apiV1NoteIdPdfGet($id);
} catch (Exception $e) {
    echo 'Exception when calling NoteApi->apiV1NoteIdPdfGet: ', $e->getMessage(), PHP_EOL;
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

## `apiV1NoteIdXmlGet()`

```php
apiV1NoteIdXmlGet($id)
```

Descargar XML firmado

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new Intifact\Sdk\Api\NoteApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$id = 'id_example'; // string

try {
    $apiInstance->apiV1NoteIdXmlGet($id);
} catch (Exception $e) {
    echo 'Exception when calling NoteApi->apiV1NoteIdXmlGet: ', $e->getMessage(), PHP_EOL;
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

## `apiV1NoteSendPost()`

```php
apiV1NoteSendPost($api_v1_note_send_post_request): \Intifact\Sdk\Model\ApiV1NoteSendPost202Response
```

Enviar nota de crédito (07) o débito (08) a SUNAT

Genera XML UBL 2.1, firma y encola. Responde 202. Consultar GET /documents/{id} para el resultado final. Idempotente por (RUC emisor, tipoDoc, serie, correlativo): reenviar el mismo comprobante NO lo duplica. Si ya fue aceptado devuelve el mismo id y hash sin reenviar nada a SUNAT; si sigue en proceso responde 409 (esperá el resultado, no cambies el correlativo). Solo un RECHAZADO exige un correlativo nuevo.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new Intifact\Sdk\Api\NoteApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$api_v1_note_send_post_request = new \Intifact\Sdk\Model\ApiV1NoteSendPostRequest(); // \Intifact\Sdk\Model\ApiV1NoteSendPostRequest

try {
    $result = $apiInstance->apiV1NoteSendPost($api_v1_note_send_post_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling NoteApi->apiV1NoteSendPost: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **api_v1_note_send_post_request** | [**\Intifact\Sdk\Model\ApiV1NoteSendPostRequest**](../Model/ApiV1NoteSendPostRequest.md)|  | |

### Return type

[**\Intifact\Sdk\Model\ApiV1NoteSendPost202Response**](../Model/ApiV1NoteSendPost202Response.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
