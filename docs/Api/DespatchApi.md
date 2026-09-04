# Intifact\Sdk\DespatchApi

Guías de Remisión (09 — GRE REST)

All URIs are relative to http://localhost:3000, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**apiV1DespatchIdCdrGet()**](DespatchApi.md#apiV1DespatchIdCdrGet) | **GET** /api/v1/despatch/{id}/cdr | Descargar CDR (constancia de SUNAT) |
| [**apiV1DespatchIdPdfGet()**](DespatchApi.md#apiV1DespatchIdPdfGet) | **GET** /api/v1/despatch/{id}/pdf | Obtener PDF de la guía (A4 oficina, ticket 80mm o 58mm POS) |
| [**apiV1DespatchIdXmlGet()**](DespatchApi.md#apiV1DespatchIdXmlGet) | **GET** /api/v1/despatch/{id}/xml | Descargar XML firmado de la guía |
| [**apiV1DespatchSendMultiPost()**](DespatchApi.md#apiV1DespatchSendMultiPost) | **POST** /api/v1/despatch/send-multi | Enviar múltiples guías de remisión por destino |
| [**apiV1DespatchSendPost()**](DespatchApi.md#apiV1DespatchSendPost) | **POST** /api/v1/despatch/send | Enviar guía de remisión (09) via API GRE REST |
| [**apiV1DespatchTransportistaSendPost()**](DespatchApi.md#apiV1DespatchTransportistaSendPost) | **POST** /api/v1/despatch-transportista/send | Enviar guía de remisión TRANSPORTISTA (31) via API GRE REST |


## `apiV1DespatchIdCdrGet()`

```php
apiV1DespatchIdCdrGet($id)
```

Descargar CDR (constancia de SUNAT)

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new Intifact\Sdk\Api\DespatchApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$id = 'id_example'; // string

try {
    $apiInstance->apiV1DespatchIdCdrGet($id);
} catch (Exception $e) {
    echo 'Exception when calling DespatchApi->apiV1DespatchIdCdrGet: ', $e->getMessage(), PHP_EOL;
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

## `apiV1DespatchIdPdfGet()`

```php
apiV1DespatchIdPdfGet($id, $format)
```

Obtener PDF de la guía (A4 oficina, ticket 80mm o 58mm POS)

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new Intifact\Sdk\Api\DespatchApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$id = 'id_example'; // string
$format = 'a4'; // string

try {
    $apiInstance->apiV1DespatchIdPdfGet($id, $format);
} catch (Exception $e) {
    echo 'Exception when calling DespatchApi->apiV1DespatchIdPdfGet: ', $e->getMessage(), PHP_EOL;
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

## `apiV1DespatchIdXmlGet()`

```php
apiV1DespatchIdXmlGet($id)
```

Descargar XML firmado de la guía

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new Intifact\Sdk\Api\DespatchApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$id = 'id_example'; // string

try {
    $apiInstance->apiV1DespatchIdXmlGet($id);
} catch (Exception $e) {
    echo 'Exception when calling DespatchApi->apiV1DespatchIdXmlGet: ', $e->getMessage(), PHP_EOL;
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

## `apiV1DespatchSendMultiPost()`

```php
apiV1DespatchSendMultiPost($api_v1_despatch_send_multi_post_request): \Intifact\Sdk\Model\ApiV1DespatchSendMultiPost202Response
```

Enviar múltiples guías de remisión por destino

Recibe datos comunes de transporte + array de destinos. Genera una guía por cada destino con correlativo auto-asignado. Cada guía se encola independientemente para envío a SUNAT GRE.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new Intifact\Sdk\Api\DespatchApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$api_v1_despatch_send_multi_post_request = new \Intifact\Sdk\Model\ApiV1DespatchSendMultiPostRequest(); // \Intifact\Sdk\Model\ApiV1DespatchSendMultiPostRequest

try {
    $result = $apiInstance->apiV1DespatchSendMultiPost($api_v1_despatch_send_multi_post_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DespatchApi->apiV1DespatchSendMultiPost: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **api_v1_despatch_send_multi_post_request** | [**\Intifact\Sdk\Model\ApiV1DespatchSendMultiPostRequest**](../Model/ApiV1DespatchSendMultiPostRequest.md)|  | |

### Return type

[**\Intifact\Sdk\Model\ApiV1DespatchSendMultiPost202Response**](../Model/ApiV1DespatchSendMultiPost202Response.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `apiV1DespatchSendPost()`

```php
apiV1DespatchSendPost($api_v1_despatch_send_post_request): \Intifact\Sdk\Model\ApiV1NoteSendPost202Response
```

Enviar guía de remisión (09) via API GRE REST

Genera XML UBL 2.1, firma y encola. El worker obtiene token OAuth2, envía a SUNAT GRE, guarda ticket y luego hace polling de getStatus. Idempotente por (RUC emisor, tipoDoc, serie, correlativo): reenviar el mismo comprobante NO lo duplica. Si ya fue aceptado devuelve el mismo id y hash sin reenviar nada a SUNAT; si sigue en proceso responde 409 (esperá el resultado, no cambies el correlativo). Solo un RECHAZADO exige un correlativo nuevo.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new Intifact\Sdk\Api\DespatchApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$api_v1_despatch_send_post_request = new \Intifact\Sdk\Model\ApiV1DespatchSendPostRequest(); // \Intifact\Sdk\Model\ApiV1DespatchSendPostRequest

try {
    $result = $apiInstance->apiV1DespatchSendPost($api_v1_despatch_send_post_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DespatchApi->apiV1DespatchSendPost: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **api_v1_despatch_send_post_request** | [**\Intifact\Sdk\Model\ApiV1DespatchSendPostRequest**](../Model/ApiV1DespatchSendPostRequest.md)|  | |

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

## `apiV1DespatchTransportistaSendPost()`

```php
apiV1DespatchTransportistaSendPost($api_v1_despatch_transportista_send_post_request): \Intifact\Sdk\Model\ApiV1NoteSendPost202Response
```

Enviar guía de remisión TRANSPORTISTA (31) via API GRE REST

Guía emitida por la empresa de transporte (emisor=transportista). Incluye remitente (dueño de los bienes) y destinatario. Genera XML UBL 2.1, firma y encola para envío a SUNAT GRE.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new Intifact\Sdk\Api\DespatchApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$api_v1_despatch_transportista_send_post_request = new \Intifact\Sdk\Model\ApiV1DespatchTransportistaSendPostRequest(); // \Intifact\Sdk\Model\ApiV1DespatchTransportistaSendPostRequest

try {
    $result = $apiInstance->apiV1DespatchTransportistaSendPost($api_v1_despatch_transportista_send_post_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DespatchApi->apiV1DespatchTransportistaSendPost: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **api_v1_despatch_transportista_send_post_request** | [**\Intifact\Sdk\Model\ApiV1DespatchTransportistaSendPostRequest**](../Model/ApiV1DespatchTransportistaSendPostRequest.md)|  | |

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
