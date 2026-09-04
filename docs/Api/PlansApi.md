# Intifact\Sdk\PlansApi



All URIs are relative to http://localhost:3000, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**apiV1PlansGet()**](PlansApi.md#apiV1PlansGet) | **GET** /api/v1/plans | Listar planes (solo master) |
| [**apiV1PlansIdDelete()**](PlansApi.md#apiV1PlansIdDelete) | **DELETE** /api/v1/plans/{id} | Desactivar plan (soft-delete) |
| [**apiV1PlansIdPut()**](PlansApi.md#apiV1PlansIdPut) | **PUT** /api/v1/plans/{id} | Actualizar plan (precio, docs, nombre, estado) |
| [**apiV1PlansPost()**](PlansApi.md#apiV1PlansPost) | **POST** /api/v1/plans | Crear plan |


## `apiV1PlansGet()`

```php
apiV1PlansGet()
```

Listar planes (solo master)

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new Intifact\Sdk\Api\PlansApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);

try {
    $apiInstance->apiV1PlansGet();
} catch (Exception $e) {
    echo 'Exception when calling PlansApi->apiV1PlansGet: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

This endpoint does not need any parameter.

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

## `apiV1PlansIdDelete()`

```php
apiV1PlansIdDelete($id)
```

Desactivar plan (soft-delete)

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new Intifact\Sdk\Api\PlansApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$id = 'id_example'; // string

try {
    $apiInstance->apiV1PlansIdDelete($id);
} catch (Exception $e) {
    echo 'Exception when calling PlansApi->apiV1PlansIdDelete: ', $e->getMessage(), PHP_EOL;
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

## `apiV1PlansIdPut()`

```php
apiV1PlansIdPut($id, $api_v1_plans_id_put_request)
```

Actualizar plan (precio, docs, nombre, estado)

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new Intifact\Sdk\Api\PlansApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$id = 'id_example'; // string
$api_v1_plans_id_put_request = new \Intifact\Sdk\Model\ApiV1PlansIdPutRequest(); // \Intifact\Sdk\Model\ApiV1PlansIdPutRequest

try {
    $apiInstance->apiV1PlansIdPut($id, $api_v1_plans_id_put_request);
} catch (Exception $e) {
    echo 'Exception when calling PlansApi->apiV1PlansIdPut: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**|  | |
| **api_v1_plans_id_put_request** | [**\Intifact\Sdk\Model\ApiV1PlansIdPutRequest**](../Model/ApiV1PlansIdPutRequest.md)|  | |

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

## `apiV1PlansPost()`

```php
apiV1PlansPost($api_v1_plans_post_request)
```

Crear plan

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new Intifact\Sdk\Api\PlansApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$api_v1_plans_post_request = new \Intifact\Sdk\Model\ApiV1PlansPostRequest(); // \Intifact\Sdk\Model\ApiV1PlansPostRequest

try {
    $apiInstance->apiV1PlansPost($api_v1_plans_post_request);
} catch (Exception $e) {
    echo 'Exception when calling PlansApi->apiV1PlansPost: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **api_v1_plans_post_request** | [**\Intifact\Sdk\Model\ApiV1PlansPostRequest**](../Model/ApiV1PlansPostRequest.md)|  | |

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
