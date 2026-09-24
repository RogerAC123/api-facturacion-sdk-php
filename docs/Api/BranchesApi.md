# Intifact\Sdk\BranchesApi

Sucursales / establecimientos anexos registrados en SUNAT SOL

All URIs are relative to http://localhost:3099, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**listBranches()**](BranchesApi.md#listBranches) | **GET** /api/v1/companies/{id}/branches | Listar establecimientos (sucursales) de una empresa |


## `listBranches()`

```php
listBranches($id)
```

Listar establecimientos (sucursales) de una empresa

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: apiKey
$config = Intifact\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Intifact\Sdk\Api\BranchesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string

try {
    $apiInstance->listBranches($id);
} catch (Exception $e) {
    echo 'Exception when calling BranchesApi->listBranches: ', $e->getMessage(), PHP_EOL;
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
