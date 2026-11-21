# Intifact\Sdk\BranchesApi

Sucursales / establecimientos anexos registrados en SUNAT SOL

All URIs are relative to http://localhost:3000, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**createBranch()**](BranchesApi.md#createBranch) | **POST** /api/v1/companies/{id}/branches | Crear establecimiento (sucursal) |
| [**deactivateBranch()**](BranchesApi.md#deactivateBranch) | **DELETE** /api/v1/companies/{id}/branches/{branchId} | Desactivar establecimiento (soft-delete) |
| [**listBranches()**](BranchesApi.md#listBranches) | **GET** /api/v1/companies/{id}/branches | Listar establecimientos (sucursales) de una empresa |
| [**updateBranch()**](BranchesApi.md#updateBranch) | **PUT** /api/v1/companies/{id}/branches/{branchId} | Actualizar establecimiento |


## `createBranch()`

```php
createBranch($id, $create_branch_request)
```

Crear establecimiento (sucursal)

El código debe coincidir con el que SUNAT asignó a la sucursal al registrarla en el portal SOL (Mis Trámites > Establecimientos Anexos).

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
$create_branch_request = new \Intifact\Sdk\Model\CreateBranchRequest(); // \Intifact\Sdk\Model\CreateBranchRequest

try {
    $apiInstance->createBranch($id, $create_branch_request);
} catch (Exception $e) {
    echo 'Exception when calling BranchesApi->createBranch: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**|  | |
| **create_branch_request** | [**\Intifact\Sdk\Model\CreateBranchRequest**](../Model/CreateBranchRequest.md)|  | |

### Return type

void (empty response body)

### Authorization

[apiKey](../../README.md#apiKey)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `deactivateBranch()`

```php
deactivateBranch($id, $branch_id)
```

Desactivar establecimiento (soft-delete)

No se elimina físicamente porque puede haber documentos emitidos desde ahí. Solo se desactiva (isActive=false).

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
$branch_id = 'branch_id_example'; // string

try {
    $apiInstance->deactivateBranch($id, $branch_id);
} catch (Exception $e) {
    echo 'Exception when calling BranchesApi->deactivateBranch: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**|  | |
| **branch_id** | **string**|  | |

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

## `updateBranch()`

```php
updateBranch($id, $branch_id, $update_branch_request)
```

Actualizar establecimiento

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
$branch_id = 'branch_id_example'; // string
$update_branch_request = new \Intifact\Sdk\Model\UpdateBranchRequest(); // \Intifact\Sdk\Model\UpdateBranchRequest

try {
    $apiInstance->updateBranch($id, $branch_id, $update_branch_request);
} catch (Exception $e) {
    echo 'Exception when calling BranchesApi->updateBranch: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**|  | |
| **branch_id** | **string**|  | |
| **update_branch_request** | [**\Intifact\Sdk\Model\UpdateBranchRequest**](../Model/UpdateBranchRequest.md)|  | |

### Return type

void (empty response body)

### Authorization

[apiKey](../../README.md#apiKey)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
