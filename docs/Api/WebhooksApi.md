# Intifact\Sdk\WebhooksApi

Suscripciones a eventos vía webhook

All URIs are relative to http://localhost:3000, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**apiV1WebhooksGet()**](WebhooksApi.md#apiV1WebhooksGet) | **GET** /api/v1/webhooks | Listar webhooks (filtra por RUC opcional) |
| [**apiV1WebhooksIdDelete()**](WebhooksApi.md#apiV1WebhooksIdDelete) | **DELETE** /api/v1/webhooks/{id} | Eliminar webhook (también elimina su historial de deliveries) |
| [**apiV1WebhooksIdDeliveriesDeliveryIdRedeliverPost()**](WebhooksApi.md#apiV1WebhooksIdDeliveriesDeliveryIdRedeliverPost) | **POST** /api/v1/webhooks/{id}/deliveries/{deliveryId}/redeliver | Reintentar manualmente una entrega |
| [**apiV1WebhooksIdDeliveriesGet()**](WebhooksApi.md#apiV1WebhooksIdDeliveriesGet) | **GET** /api/v1/webhooks/{id}/deliveries | Log de entregas del webhook |
| [**apiV1WebhooksIdGet()**](WebhooksApi.md#apiV1WebhooksIdGet) | **GET** /api/v1/webhooks/{id} | Detalle de webhook (sin secret) |
| [**apiV1WebhooksIdPut()**](WebhooksApi.md#apiV1WebhooksIdPut) | **PUT** /api/v1/webhooks/{id} | Actualizar webhook (url, eventos, activación) |
| [**apiV1WebhooksIdRotateSecretPost()**](WebhooksApi.md#apiV1WebhooksIdRotateSecretPost) | **POST** /api/v1/webhooks/{id}/rotate-secret | Rotar el secret de firma (devuelto UNA sola vez) |
| [**apiV1WebhooksIdTestPost()**](WebhooksApi.md#apiV1WebhooksIdTestPost) | **POST** /api/v1/webhooks/{id}/test | Enviar un evento de prueba (webhook.test) |
| [**apiV1WebhooksPost()**](WebhooksApi.md#apiV1WebhooksPost) | **POST** /api/v1/webhooks | Crear endpoint webhook |


## `apiV1WebhooksGet()`

```php
apiV1WebhooksGet($ruc)
```

Listar webhooks (filtra por RUC opcional)

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new Intifact\Sdk\Api\WebhooksApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$ruc = 'ruc_example'; // string

try {
    $apiInstance->apiV1WebhooksGet($ruc);
} catch (Exception $e) {
    echo 'Exception when calling WebhooksApi->apiV1WebhooksGet: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **ruc** | **string**|  | [optional] |

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

## `apiV1WebhooksIdDelete()`

```php
apiV1WebhooksIdDelete($id)
```

Eliminar webhook (también elimina su historial de deliveries)

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new Intifact\Sdk\Api\WebhooksApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$id = 'id_example'; // string

try {
    $apiInstance->apiV1WebhooksIdDelete($id);
} catch (Exception $e) {
    echo 'Exception when calling WebhooksApi->apiV1WebhooksIdDelete: ', $e->getMessage(), PHP_EOL;
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

## `apiV1WebhooksIdDeliveriesDeliveryIdRedeliverPost()`

```php
apiV1WebhooksIdDeliveriesDeliveryIdRedeliverPost($id, $delivery_id)
```

Reintentar manualmente una entrega

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new Intifact\Sdk\Api\WebhooksApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$id = 'id_example'; // string
$delivery_id = 'delivery_id_example'; // string

try {
    $apiInstance->apiV1WebhooksIdDeliveriesDeliveryIdRedeliverPost($id, $delivery_id);
} catch (Exception $e) {
    echo 'Exception when calling WebhooksApi->apiV1WebhooksIdDeliveriesDeliveryIdRedeliverPost: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**|  | |
| **delivery_id** | **string**|  | |

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

## `apiV1WebhooksIdDeliveriesGet()`

```php
apiV1WebhooksIdDeliveriesGet($id, $limit, $success)
```

Log de entregas del webhook

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new Intifact\Sdk\Api\WebhooksApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$id = 'id_example'; // string
$limit = 50; // int
$success = 'success_example'; // string

try {
    $apiInstance->apiV1WebhooksIdDeliveriesGet($id, $limit, $success);
} catch (Exception $e) {
    echo 'Exception when calling WebhooksApi->apiV1WebhooksIdDeliveriesGet: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**|  | |
| **limit** | **int**|  | [optional] [default to 50] |
| **success** | **string**|  | [optional] |

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

## `apiV1WebhooksIdGet()`

```php
apiV1WebhooksIdGet($id)
```

Detalle de webhook (sin secret)

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new Intifact\Sdk\Api\WebhooksApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$id = 'id_example'; // string

try {
    $apiInstance->apiV1WebhooksIdGet($id);
} catch (Exception $e) {
    echo 'Exception when calling WebhooksApi->apiV1WebhooksIdGet: ', $e->getMessage(), PHP_EOL;
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

## `apiV1WebhooksIdPut()`

```php
apiV1WebhooksIdPut($id, $api_v1_webhooks_id_put_request)
```

Actualizar webhook (url, eventos, activación)

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new Intifact\Sdk\Api\WebhooksApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$id = 'id_example'; // string
$api_v1_webhooks_id_put_request = new \Intifact\Sdk\Model\ApiV1WebhooksIdPutRequest(); // \Intifact\Sdk\Model\ApiV1WebhooksIdPutRequest

try {
    $apiInstance->apiV1WebhooksIdPut($id, $api_v1_webhooks_id_put_request);
} catch (Exception $e) {
    echo 'Exception when calling WebhooksApi->apiV1WebhooksIdPut: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**|  | |
| **api_v1_webhooks_id_put_request** | [**\Intifact\Sdk\Model\ApiV1WebhooksIdPutRequest**](../Model/ApiV1WebhooksIdPutRequest.md)|  | |

### Return type

void (empty response body)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: Not defined

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `apiV1WebhooksIdRotateSecretPost()`

```php
apiV1WebhooksIdRotateSecretPost($id)
```

Rotar el secret de firma (devuelto UNA sola vez)

Genera un nuevo secret HMAC y lo devuelve una única vez. Las firmas de entregas posteriores usarán el nuevo secret; actualiza tu receptor antes de rotar.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new Intifact\Sdk\Api\WebhooksApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$id = 'id_example'; // string

try {
    $apiInstance->apiV1WebhooksIdRotateSecretPost($id);
} catch (Exception $e) {
    echo 'Exception when calling WebhooksApi->apiV1WebhooksIdRotateSecretPost: ', $e->getMessage(), PHP_EOL;
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

## `apiV1WebhooksIdTestPost()`

```php
apiV1WebhooksIdTestPost($id)
```

Enviar un evento de prueba (webhook.test)

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new Intifact\Sdk\Api\WebhooksApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$id = 'id_example'; // string

try {
    $apiInstance->apiV1WebhooksIdTestPost($id);
} catch (Exception $e) {
    echo 'Exception when calling WebhooksApi->apiV1WebhooksIdTestPost: ', $e->getMessage(), PHP_EOL;
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

## `apiV1WebhooksPost()`

```php
apiV1WebhooksPost($api_v1_webhooks_post_request)
```

Crear endpoint webhook

Registra una URL que recibirá POSTs cuando ocurran los eventos suscritos. Sin `empresaRuc` el webhook cubre TODAS las empresas de tu cuenta (un solo secret; el `empresaRuc` viaja en cada payload). La respuesta incluye el `secret` (mostrado UNA sola vez) — guárdalo para verificar las firmas HMAC-SHA256.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new Intifact\Sdk\Api\WebhooksApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$api_v1_webhooks_post_request = new \Intifact\Sdk\Model\ApiV1WebhooksPostRequest(); // \Intifact\Sdk\Model\ApiV1WebhooksPostRequest

try {
    $apiInstance->apiV1WebhooksPost($api_v1_webhooks_post_request);
} catch (Exception $e) {
    echo 'Exception when calling WebhooksApi->apiV1WebhooksPost: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **api_v1_webhooks_post_request** | [**\Intifact\Sdk\Model\ApiV1WebhooksPostRequest**](../Model/ApiV1WebhooksPostRequest.md)|  | |

### Return type

void (empty response body)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: Not defined

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
