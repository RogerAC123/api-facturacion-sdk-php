# Intifact\Sdk\CompanyApi

CRUD de empresas emisoras

All URIs are relative to http://localhost:3000, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**deleteCompanyLogo()**](CompanyApi.md#deleteCompanyLogo) | **DELETE** /api/v1/companies/{id}/logo | Eliminar logo de la empresa |
| [**getCompany()**](CompanyApi.md#getCompany) | **GET** /api/v1/companies/{id} | Detalle de empresa |
| [**getCompanyLogo()**](CompanyApi.md#getCompanyLogo) | **GET** /api/v1/companies/{id}/logo | Obtener logo de la empresa (PNG/JPG) |
| [**listCompanies()**](CompanyApi.md#listCompanies) | **GET** /api/v1/companies | Listar empresas emisoras |
| [**registerCompany()**](CompanyApi.md#registerCompany) | **POST** /api/v1/companies/register | Dar de alta una empresa con su certificado digital |
| [**updateCompany()**](CompanyApi.md#updateCompany) | **PUT** /api/v1/companies/{id} | Actualizar empresa |
| [**uploadCompanyCertificate()**](CompanyApi.md#uploadCompanyCertificate) | **POST** /api/v1/companies/{id}/certificate | Subir certificado digital (.p12/.pfx en base64) |
| [**uploadCompanyLogo()**](CompanyApi.md#uploadCompanyLogo) | **POST** /api/v1/companies/{id}/logo | Subir logo de la empresa (PNG/JPG, max 200KB) |


## `deleteCompanyLogo()`

```php
deleteCompanyLogo($id)
```

Eliminar logo de la empresa

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: apiKey
$config = Intifact\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Intifact\Sdk\Api\CompanyApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string

try {
    $apiInstance->deleteCompanyLogo($id);
} catch (Exception $e) {
    echo 'Exception when calling CompanyApi->deleteCompanyLogo: ', $e->getMessage(), PHP_EOL;
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

## `getCompany()`

```php
getCompany($id)
```

Detalle de empresa

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: apiKey
$config = Intifact\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Intifact\Sdk\Api\CompanyApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string

try {
    $apiInstance->getCompany($id);
} catch (Exception $e) {
    echo 'Exception when calling CompanyApi->getCompany: ', $e->getMessage(), PHP_EOL;
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

## `getCompanyLogo()`

```php
getCompanyLogo($id)
```

Obtener logo de la empresa (PNG/JPG)

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: apiKey
$config = Intifact\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Intifact\Sdk\Api\CompanyApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string

try {
    $apiInstance->getCompanyLogo($id);
} catch (Exception $e) {
    echo 'Exception when calling CompanyApi->getCompanyLogo: ', $e->getMessage(), PHP_EOL;
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

## `listCompanies()`

```php
listCompanies()
```

Listar empresas emisoras

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: apiKey
$config = Intifact\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Intifact\Sdk\Api\CompanyApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);

try {
    $apiInstance->listCompanies();
} catch (Exception $e) {
    echo 'Exception when calling CompanyApi->listCompanies: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

This endpoint does not need any parameter.

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

## `registerCompany()`

```php
registerCompany($register_company_request)
```

Dar de alta una empresa con su certificado digital

Requiere una API key live de cuenta en un plan pago (autogestión incluida). El certificado (.p12/.pfx en base64) tiene que declarar el mismo RUC; si no, no se crea nada.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: apiKey
$config = Intifact\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Intifact\Sdk\Api\CompanyApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$register_company_request = new \Intifact\Sdk\Model\RegisterCompanyRequest(); // \Intifact\Sdk\Model\RegisterCompanyRequest

try {
    $apiInstance->registerCompany($register_company_request);
} catch (Exception $e) {
    echo 'Exception when calling CompanyApi->registerCompany: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **register_company_request** | [**\Intifact\Sdk\Model\RegisterCompanyRequest**](../Model/RegisterCompanyRequest.md)|  | |

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

## `updateCompany()`

```php
updateCompany($id, $update_company_request)
```

Actualizar empresa

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: apiKey
$config = Intifact\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Intifact\Sdk\Api\CompanyApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string
$update_company_request = new \Intifact\Sdk\Model\UpdateCompanyRequest(); // \Intifact\Sdk\Model\UpdateCompanyRequest

try {
    $apiInstance->updateCompany($id, $update_company_request);
} catch (Exception $e) {
    echo 'Exception when calling CompanyApi->updateCompany: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**|  | |
| **update_company_request** | [**\Intifact\Sdk\Model\UpdateCompanyRequest**](../Model/UpdateCompanyRequest.md)|  | |

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

## `uploadCompanyCertificate()`

```php
uploadCompanyCertificate($id, $upload_company_certificate_request)
```

Subir certificado digital (.p12/.pfx en base64)

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: apiKey
$config = Intifact\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Intifact\Sdk\Api\CompanyApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string
$upload_company_certificate_request = new \Intifact\Sdk\Model\UploadCompanyCertificateRequest(); // \Intifact\Sdk\Model\UploadCompanyCertificateRequest

try {
    $apiInstance->uploadCompanyCertificate($id, $upload_company_certificate_request);
} catch (Exception $e) {
    echo 'Exception when calling CompanyApi->uploadCompanyCertificate: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**|  | |
| **upload_company_certificate_request** | [**\Intifact\Sdk\Model\UploadCompanyCertificateRequest**](../Model/UploadCompanyCertificateRequest.md)|  | |

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

## `uploadCompanyLogo()`

```php
uploadCompanyLogo($id)
```

Subir logo de la empresa (PNG/JPG, max 200KB)

El logo aparecerá en los PDFs (A4 y ticket). Reemplaza el anterior.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: apiKey
$config = Intifact\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Intifact\Sdk\Api\CompanyApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string

try {
    $apiInstance->uploadCompanyLogo($id);
} catch (Exception $e) {
    echo 'Exception when calling CompanyApi->uploadCompanyLogo: ', $e->getMessage(), PHP_EOL;
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
