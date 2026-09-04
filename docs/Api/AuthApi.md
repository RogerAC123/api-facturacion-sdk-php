# Intifact\Sdk\AuthApi

Signup, login y sesión de usuarios humanos

All URIs are relative to http://localhost:3000, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**apiV1AuthLoginPost()**](AuthApi.md#apiV1AuthLoginPost) | **POST** /api/v1/auth/login | Login email+password |
| [**apiV1AuthLogoutPost()**](AuthApi.md#apiV1AuthLogoutPost) | **POST** /api/v1/auth/logout | Cerrar sesión actual (revoca refresh) |
| [**apiV1AuthMeGet()**](AuthApi.md#apiV1AuthMeGet) | **GET** /api/v1/auth/me | Datos del usuario actual |
| [**apiV1AuthRefreshPost()**](AuthApi.md#apiV1AuthRefreshPost) | **POST** /api/v1/auth/refresh | Renovar access token con refresh cookie |
| [**apiV1AuthSessionsGet()**](AuthApi.md#apiV1AuthSessionsGet) | **GET** /api/v1/auth/sessions | Lista de sesiones activas del usuario |
| [**apiV1AuthSessionsIdDelete()**](AuthApi.md#apiV1AuthSessionsIdDelete) | **DELETE** /api/v1/auth/sessions/{id} | Revocar una sesión activa por ID |
| [**apiV1AuthSignupPost()**](AuthApi.md#apiV1AuthSignupPost) | **POST** /api/v1/auth/signup | Registro público: crea Tenant + User + sesión |
| [**apiV1AuthVerifyEmailGet()**](AuthApi.md#apiV1AuthVerifyEmailGet) | **GET** /api/v1/auth/verify-email | Confirmar email con token (one-time, 24h) |
| [**apiV1AuthVerifyEmailResendPost()**](AuthApi.md#apiV1AuthVerifyEmailResendPost) | **POST** /api/v1/auth/verify-email/resend | Re-enviar email de verificación al usuario logueado |


## `apiV1AuthLoginPost()`

```php
apiV1AuthLoginPost($api_v1_auth_login_post_request)
```

Login email+password

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new Intifact\Sdk\Api\AuthApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$api_v1_auth_login_post_request = new \Intifact\Sdk\Model\ApiV1AuthLoginPostRequest(); // \Intifact\Sdk\Model\ApiV1AuthLoginPostRequest

try {
    $apiInstance->apiV1AuthLoginPost($api_v1_auth_login_post_request);
} catch (Exception $e) {
    echo 'Exception when calling AuthApi->apiV1AuthLoginPost: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **api_v1_auth_login_post_request** | [**\Intifact\Sdk\Model\ApiV1AuthLoginPostRequest**](../Model/ApiV1AuthLoginPostRequest.md)|  | |

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

## `apiV1AuthLogoutPost()`

```php
apiV1AuthLogoutPost()
```

Cerrar sesión actual (revoca refresh)

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new Intifact\Sdk\Api\AuthApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);

try {
    $apiInstance->apiV1AuthLogoutPost();
} catch (Exception $e) {
    echo 'Exception when calling AuthApi->apiV1AuthLogoutPost: ', $e->getMessage(), PHP_EOL;
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

## `apiV1AuthMeGet()`

```php
apiV1AuthMeGet()
```

Datos del usuario actual

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new Intifact\Sdk\Api\AuthApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);

try {
    $apiInstance->apiV1AuthMeGet();
} catch (Exception $e) {
    echo 'Exception when calling AuthApi->apiV1AuthMeGet: ', $e->getMessage(), PHP_EOL;
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

## `apiV1AuthRefreshPost()`

```php
apiV1AuthRefreshPost()
```

Renovar access token con refresh cookie

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new Intifact\Sdk\Api\AuthApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);

try {
    $apiInstance->apiV1AuthRefreshPost();
} catch (Exception $e) {
    echo 'Exception when calling AuthApi->apiV1AuthRefreshPost: ', $e->getMessage(), PHP_EOL;
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

## `apiV1AuthSessionsGet()`

```php
apiV1AuthSessionsGet()
```

Lista de sesiones activas del usuario

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new Intifact\Sdk\Api\AuthApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);

try {
    $apiInstance->apiV1AuthSessionsGet();
} catch (Exception $e) {
    echo 'Exception when calling AuthApi->apiV1AuthSessionsGet: ', $e->getMessage(), PHP_EOL;
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

## `apiV1AuthSessionsIdDelete()`

```php
apiV1AuthSessionsIdDelete($id)
```

Revocar una sesión activa por ID

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new Intifact\Sdk\Api\AuthApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$id = 'id_example'; // string

try {
    $apiInstance->apiV1AuthSessionsIdDelete($id);
} catch (Exception $e) {
    echo 'Exception when calling AuthApi->apiV1AuthSessionsIdDelete: ', $e->getMessage(), PHP_EOL;
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

## `apiV1AuthSignupPost()`

```php
apiV1AuthSignupPost($api_v1_auth_signup_post_request)
```

Registro público: crea Tenant + User + sesión

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new Intifact\Sdk\Api\AuthApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$api_v1_auth_signup_post_request = new \Intifact\Sdk\Model\ApiV1AuthSignupPostRequest(); // \Intifact\Sdk\Model\ApiV1AuthSignupPostRequest

try {
    $apiInstance->apiV1AuthSignupPost($api_v1_auth_signup_post_request);
} catch (Exception $e) {
    echo 'Exception when calling AuthApi->apiV1AuthSignupPost: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **api_v1_auth_signup_post_request** | [**\Intifact\Sdk\Model\ApiV1AuthSignupPostRequest**](../Model/ApiV1AuthSignupPostRequest.md)|  | |

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

## `apiV1AuthVerifyEmailGet()`

```php
apiV1AuthVerifyEmailGet($token)
```

Confirmar email con token (one-time, 24h)

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new Intifact\Sdk\Api\AuthApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$token = 'token_example'; // string

try {
    $apiInstance->apiV1AuthVerifyEmailGet($token);
} catch (Exception $e) {
    echo 'Exception when calling AuthApi->apiV1AuthVerifyEmailGet: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **token** | **string**|  | |

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

## `apiV1AuthVerifyEmailResendPost()`

```php
apiV1AuthVerifyEmailResendPost()
```

Re-enviar email de verificación al usuario logueado

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new Intifact\Sdk\Api\AuthApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);

try {
    $apiInstance->apiV1AuthVerifyEmailResendPost();
} catch (Exception $e) {
    echo 'Exception when calling AuthApi->apiV1AuthVerifyEmailResendPost: ', $e->getMessage(), PHP_EOL;
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
