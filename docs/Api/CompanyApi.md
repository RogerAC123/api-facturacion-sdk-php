# Intifact\Sdk\CompanyApi

CRUD de empresas emisoras

All URIs are relative to http://localhost:3000, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**apiV1CompaniesClaimPost()**](CompanyApi.md#apiV1CompaniesClaimPost) | **POST** /api/v1/companies/claim | Reclamar un RUC registrado por otra cuenta, con su certificado |
| [**apiV1CompaniesGet()**](CompanyApi.md#apiV1CompaniesGet) | **GET** /api/v1/companies | Listar empresas emisoras |
| [**apiV1CompaniesIdGet()**](CompanyApi.md#apiV1CompaniesIdGet) | **GET** /api/v1/companies/{id} | Detalle de empresa |
| [**apiV1CompaniesIdLogoGet()**](CompanyApi.md#apiV1CompaniesIdLogoGet) | **GET** /api/v1/companies/{id}/logo | Obtener logo de la empresa (PNG/JPG) |
| [**apiV1CompaniesIdPut()**](CompanyApi.md#apiV1CompaniesIdPut) | **PUT** /api/v1/companies/{id} | Actualizar empresa |
| [**apiV1CompaniesPost()**](CompanyApi.md#apiV1CompaniesPost) | **POST** /api/v1/companies | Crear empresa emisora |


## `apiV1CompaniesClaimPost()`

```php
apiV1CompaniesClaimPost($api_v1_companies_claim_post_request)
```

Reclamar un RUC registrado por otra cuenta, con su certificado

Prueba de titularidad = certificado digital del RUC. Si la cuenta que lo tiene no acreditó titularidad y no emitió documentos, el RUC pasa a tu cuenta.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new Intifact\Sdk\Api\CompanyApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$api_v1_companies_claim_post_request = new \Intifact\Sdk\Model\ApiV1CompaniesClaimPostRequest(); // \Intifact\Sdk\Model\ApiV1CompaniesClaimPostRequest

try {
    $apiInstance->apiV1CompaniesClaimPost($api_v1_companies_claim_post_request);
} catch (Exception $e) {
    echo 'Exception when calling CompanyApi->apiV1CompaniesClaimPost: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **api_v1_companies_claim_post_request** | [**\Intifact\Sdk\Model\ApiV1CompaniesClaimPostRequest**](../Model/ApiV1CompaniesClaimPostRequest.md)|  | |

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

## `apiV1CompaniesGet()`

```php
apiV1CompaniesGet()
```

Listar empresas emisoras

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new Intifact\Sdk\Api\CompanyApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);

try {
    $apiInstance->apiV1CompaniesGet();
} catch (Exception $e) {
    echo 'Exception when calling CompanyApi->apiV1CompaniesGet: ', $e->getMessage(), PHP_EOL;
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

## `apiV1CompaniesIdGet()`

```php
apiV1CompaniesIdGet($id)
```

Detalle de empresa

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new Intifact\Sdk\Api\CompanyApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$id = 'id_example'; // string

try {
    $apiInstance->apiV1CompaniesIdGet($id);
} catch (Exception $e) {
    echo 'Exception when calling CompanyApi->apiV1CompaniesIdGet: ', $e->getMessage(), PHP_EOL;
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

## `apiV1CompaniesIdLogoGet()`

```php
apiV1CompaniesIdLogoGet($id)
```

Obtener logo de la empresa (PNG/JPG)

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new Intifact\Sdk\Api\CompanyApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$id = 'id_example'; // string

try {
    $apiInstance->apiV1CompaniesIdLogoGet($id);
} catch (Exception $e) {
    echo 'Exception when calling CompanyApi->apiV1CompaniesIdLogoGet: ', $e->getMessage(), PHP_EOL;
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

## `apiV1CompaniesIdPut()`

```php
apiV1CompaniesIdPut($id, $api_v1_companies_id_put_request)
```

Actualizar empresa

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new Intifact\Sdk\Api\CompanyApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$id = 'id_example'; // string
$api_v1_companies_id_put_request = new \Intifact\Sdk\Model\ApiV1CompaniesIdPutRequest(); // \Intifact\Sdk\Model\ApiV1CompaniesIdPutRequest

try {
    $apiInstance->apiV1CompaniesIdPut($id, $api_v1_companies_id_put_request);
} catch (Exception $e) {
    echo 'Exception when calling CompanyApi->apiV1CompaniesIdPut: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**|  | |
| **api_v1_companies_id_put_request** | [**\Intifact\Sdk\Model\ApiV1CompaniesIdPutRequest**](../Model/ApiV1CompaniesIdPutRequest.md)|  | |

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

## `apiV1CompaniesPost()`

```php
apiV1CompaniesPost($api_v1_companies_post_request)
```

Crear empresa emisora

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new Intifact\Sdk\Api\CompanyApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$api_v1_companies_post_request = new \Intifact\Sdk\Model\ApiV1CompaniesPostRequest(); // \Intifact\Sdk\Model\ApiV1CompaniesPostRequest

try {
    $apiInstance->apiV1CompaniesPost($api_v1_companies_post_request);
} catch (Exception $e) {
    echo 'Exception when calling CompanyApi->apiV1CompaniesPost: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **api_v1_companies_post_request** | [**\Intifact\Sdk\Model\ApiV1CompaniesPostRequest**](../Model/ApiV1CompaniesPostRequest.md)|  | |

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
