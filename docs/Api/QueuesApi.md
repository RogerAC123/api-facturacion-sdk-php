# Intifact\Sdk\QueuesApi

Estado de las colas BullMQ

All URIs are relative to http://localhost:3000, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**getQueueStats()**](QueuesApi.md#getQueueStats) | **GET** /api/v1/queues/stats | Estado de las colas BullMQ |


## `getQueueStats()`

```php
getQueueStats(): \Intifact\Sdk\Model\GetQueueStats200Response
```

Estado de las colas BullMQ

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: apiKey
$config = Intifact\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Intifact\Sdk\Api\QueuesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);

try {
    $result = $apiInstance->getQueueStats();
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling QueuesApi->getQueueStats: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**\Intifact\Sdk\Model\GetQueueStats200Response**](../Model/GetQueueStats200Response.md)

### Authorization

[apiKey](../../README.md#apiKey)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
