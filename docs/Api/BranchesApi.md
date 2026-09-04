# Intifact\Sdk\BranchesApi

Sucursales / establecimientos anexos registrados en SUNAT SOL

All URIs are relative to http://localhost:3000, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**apiV1CompaniesIdBranchesBranchIdDelete()**](BranchesApi.md#apiV1CompaniesIdBranchesBranchIdDelete) | **DELETE** /api/v1/companies/{id}/branches/{branchId} | Desactivar establecimiento (soft-delete) |
| [**apiV1CompaniesIdBranchesBranchIdPut()**](BranchesApi.md#apiV1CompaniesIdBranchesBranchIdPut) | **PUT** /api/v1/companies/{id}/branches/{branchId} | Actualizar establecimiento |
| [**apiV1CompaniesIdBranchesGet()**](BranchesApi.md#apiV1CompaniesIdBranchesGet) | **GET** /api/v1/companies/{id}/branches | Listar establecimientos (sucursales) de una empresa |
| [**apiV1CompaniesIdBranchesPost()**](BranchesApi.md#apiV1CompaniesIdBranchesPost) | **POST** /api/v1/companies/{id}/branches | Crear establecimiento (sucursal) |


## `apiV1CompaniesIdBranchesBranchIdDelete()`

```php
apiV1CompaniesIdBranchesBranchIdDelete($id, $branch_id)
```

Desactivar establecimiento (soft-delete)

No se elimina físicamente porque puede haber documentos emitidos desde ahí. Solo se desactiva (isActive=false).

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new Intifact\Sdk\Api\BranchesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$id = 'id_example'; // string
$branch_id = 'branch_id_example'; // string

try {
    $apiInstance->apiV1CompaniesIdBranchesBranchIdDelete($id, $branch_id);
} catch (Exception $e) {
    echo 'Exception when calling BranchesApi->apiV1CompaniesIdBranchesBranchIdDelete: ', $e->getMessage(), PHP_EOL;
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

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: Not defined

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `apiV1CompaniesIdBranchesBranchIdPut()`

```php
apiV1CompaniesIdBranchesBranchIdPut($id, $branch_id, $api_v1_companies_id_branches_branch_id_put_request)
```

Actualizar establecimiento

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new Intifact\Sdk\Api\BranchesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$id = 'id_example'; // string
$branch_id = 'branch_id_example'; // string
$api_v1_companies_id_branches_branch_id_put_request = new \Intifact\Sdk\Model\ApiV1CompaniesIdBranchesBranchIdPutRequest(); // \Intifact\Sdk\Model\ApiV1CompaniesIdBranchesBranchIdPutRequest

try {
    $apiInstance->apiV1CompaniesIdBranchesBranchIdPut($id, $branch_id, $api_v1_companies_id_branches_branch_id_put_request);
} catch (Exception $e) {
    echo 'Exception when calling BranchesApi->apiV1CompaniesIdBranchesBranchIdPut: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**|  | |
| **branch_id** | **string**|  | |
| **api_v1_companies_id_branches_branch_id_put_request** | [**\Intifact\Sdk\Model\ApiV1CompaniesIdBranchesBranchIdPutRequest**](../Model/ApiV1CompaniesIdBranchesBranchIdPutRequest.md)|  | |

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

## `apiV1CompaniesIdBranchesGet()`

```php
apiV1CompaniesIdBranchesGet($id)
```

Listar establecimientos (sucursales) de una empresa

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new Intifact\Sdk\Api\BranchesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$id = 'id_example'; // string

try {
    $apiInstance->apiV1CompaniesIdBranchesGet($id);
} catch (Exception $e) {
    echo 'Exception when calling BranchesApi->apiV1CompaniesIdBranchesGet: ', $e->getMessage(), PHP_EOL;
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

## `apiV1CompaniesIdBranchesPost()`

```php
apiV1CompaniesIdBranchesPost($id, $api_v1_companies_id_branches_post_request)
```

Crear establecimiento (sucursal)

El código debe coincidir con el que SUNAT asignó a la sucursal al registrarla en el portal SOL (Mis Trámites > Establecimientos Anexos).

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new Intifact\Sdk\Api\BranchesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$id = 'id_example'; // string
$api_v1_companies_id_branches_post_request = new \Intifact\Sdk\Model\ApiV1CompaniesIdBranchesPostRequest(); // \Intifact\Sdk\Model\ApiV1CompaniesIdBranchesPostRequest

try {
    $apiInstance->apiV1CompaniesIdBranchesPost($id, $api_v1_companies_id_branches_post_request);
} catch (Exception $e) {
    echo 'Exception when calling BranchesApi->apiV1CompaniesIdBranchesPost: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**|  | |
| **api_v1_companies_id_branches_post_request** | [**\Intifact\Sdk\Model\ApiV1CompaniesIdBranchesPostRequest**](../Model/ApiV1CompaniesIdBranchesPostRequest.md)|  | |

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
