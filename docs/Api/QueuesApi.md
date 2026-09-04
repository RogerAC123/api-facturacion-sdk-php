# Intifact\Sdk\QueuesApi

Estado de las colas BullMQ

All URIs are relative to http://localhost:3000, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**apiV1QueuesStatsGet()**](QueuesApi.md#apiV1QueuesStatsGet) | **GET** /api/v1/queues/stats | Estado de las colas BullMQ |


## `apiV1QueuesStatsGet()`

```php
apiV1QueuesStatsGet(): \Intifact\Sdk\Model\ApiV1QueuesStatsGet200Response
```

Estado de las colas BullMQ

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new Intifact\Sdk\Api\QueuesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);

try {
    $result = $apiInstance->apiV1QueuesStatsGet();
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling QueuesApi->apiV1QueuesStatsGet: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**\Intifact\Sdk\Model\ApiV1QueuesStatsGet200Response**](../Model/ApiV1QueuesStatsGet200Response.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
