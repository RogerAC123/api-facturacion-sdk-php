# Intifact\Sdk\SystemApi

Health check / utilidades

All URIs are relative to http://localhost:3099, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**exportProductoSunat()**](SystemApi.md#exportProductoSunat) | **GET** /api/v1/catalogs/producto/export | Descargar el Catálogo 25 completo (52.840 códigos) |
| [**getCatalog()**](SystemApi.md#getCatalog) | **GET** /api/v1/catalogs/{key} | Obtener un catálogo por clave |
| [**getProductoSunat()**](SystemApi.md#getProductoSunat) | **GET** /api/v1/catalogs/producto/{codigo} | Obtener un Código de Producto SUNAT por código |
| [**healthGet()**](SystemApi.md#healthGet) | **GET** /health | Health check del servicio (DB + Redis + SUNAT env) |
| [**internalCertificatesExpiringGet()**](SystemApi.md#internalCertificatesExpiringGet) | **GET** /internal/certificates/expiring | List certificates expiring within N days (internal) |
| [**internalWebhooksStatsGet()**](SystemApi.md#internalWebhooksStatsGet) | **GET** /internal/webhooks/stats | Webhook delivery statistics (internal) |
| [**listCatalogs()**](SystemApi.md#listCatalogs) | **GET** /api/v1/catalogs | Listar catálogos SUNAT (código → descripción) |
| [**searchProductoSunat()**](SystemApi.md#searchProductoSunat) | **GET** /api/v1/catalogs/producto/search | Buscar Código de Producto SUNAT (Catálogo 25 / UNSPSC) |


## `exportProductoSunat()`

```php
exportProductoSunat(): \Intifact\Sdk\Model\ExportProductoSunat200Response
```

Descargar el Catálogo 25 completo (52.840 códigos)

Devuelve `{ success, data: { version, total, items[] } }` con TODO el catálogo, en el mismo shape que devuelve la búsqueda. Pensado para cachearlo del lado del integrador: manda `If-None-Match` con el ETag recibido y la API responde 304 si nada cambió. Se sirve con `Content-Encoding: gzip` si el cliente lo acepta (~600 KB vs ~8 MB).

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: apiKey
$config = Intifact\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Intifact\Sdk\Api\SystemApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);

try {
    $result = $apiInstance->exportProductoSunat();
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling SystemApi->exportProductoSunat: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**\Intifact\Sdk\Model\ExportProductoSunat200Response**](../Model/ExportProductoSunat200Response.md)

### Authorization

[apiKey](../../README.md#apiKey)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getCatalog()`

```php
getCatalog($key)
```

Obtener un catálogo por clave

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: apiKey
$config = Intifact\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Intifact\Sdk\Api\SystemApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$key = 'key_example'; // string

try {
    $apiInstance->getCatalog($key);
} catch (Exception $e) {
    echo 'Exception when calling SystemApi->getCatalog: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **key** | **string**|  | |

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

## `getProductoSunat()`

```php
getProductoSunat($codigo): \Intifact\Sdk\Model\GetProductoSunat200Response
```

Obtener un Código de Producto SUNAT por código

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: apiKey
$config = Intifact\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Intifact\Sdk\Api\SystemApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$codigo = 'codigo_example'; // string

try {
    $result = $apiInstance->getProductoSunat($codigo);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling SystemApi->getProductoSunat: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **codigo** | **string**|  | |

### Return type

[**\Intifact\Sdk\Model\GetProductoSunat200Response**](../Model/GetProductoSunat200Response.md)

### Authorization

[apiKey](../../README.md#apiKey)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `healthGet()`

```php
healthGet()
```

Health check del servicio (DB + Redis + SUNAT env)

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new Intifact\Sdk\Api\SystemApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);

try {
    $apiInstance->healthGet();
} catch (Exception $e) {
    echo 'Exception when calling SystemApi->healthGet: ', $e->getMessage(), PHP_EOL;
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

## `internalCertificatesExpiringGet()`

```php
internalCertificatesExpiringGet($days)
```

List certificates expiring within N days (internal)

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: apiKey
$config = Intifact\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Intifact\Sdk\Api\SystemApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$days = 30; // int

try {
    $apiInstance->internalCertificatesExpiringGet($days);
} catch (Exception $e) {
    echo 'Exception when calling SystemApi->internalCertificatesExpiringGet: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **days** | **int**|  | [optional] [default to 30] |

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

## `internalWebhooksStatsGet()`

```php
internalWebhooksStatsGet($days)
```

Webhook delivery statistics (internal)

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: apiKey
$config = Intifact\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Intifact\Sdk\Api\SystemApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$days = 7; // int

try {
    $apiInstance->internalWebhooksStatsGet($days);
} catch (Exception $e) {
    echo 'Exception when calling SystemApi->internalWebhooksStatsGet: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **days** | **int**|  | [optional] [default to 7] |

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

## `listCatalogs()`

```php
listCatalogs(): \Intifact\Sdk\Model\ListCatalogs200Response
```

Listar catálogos SUNAT (código → descripción)

Devuelve los catálogos SUNAT más usados y los específicos de guías de remisión (01 tipo doc, 06 doc identidad, 18 modalidad, 20 motivo traslado, 61 doc relacionado, 07 afectación IGV, 25 unidad, etc.).

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: apiKey
$config = Intifact\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Intifact\Sdk\Api\SystemApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);

try {
    $result = $apiInstance->listCatalogs();
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling SystemApi->listCatalogs: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**\Intifact\Sdk\Model\ListCatalogs200Response**](../Model/ListCatalogs200Response.md)

### Authorization

[apiKey](../../README.md#apiKey)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `searchProductoSunat()`

```php
searchProductoSunat($q, $nivel, $limit): \Intifact\Sdk\Model\SearchProductoSunat200Response
```

Buscar Código de Producto SUNAT (Catálogo 25 / UNSPSC)

Busca por texto libre (sin distinguir tildes ni mayúsculas, todos los términos deben aparecer) o por prefijo de código si `q` son dígitos. Devuelve primero las CLASE: SUNAT exige llegar como mínimo a ese nivel y es la respuesta correcta en la mayoría de casos.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: apiKey
$config = Intifact\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Intifact\Sdk\Api\SystemApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$q = 'q_example'; // string
$nivel = 'nivel_example'; // string
$limit = 20; // int

try {
    $result = $apiInstance->searchProductoSunat($q, $nivel, $limit);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling SystemApi->searchProductoSunat: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **q** | **string**|  | |
| **nivel** | **string**|  | [optional] |
| **limit** | **int**|  | [optional] [default to 20] |

### Return type

[**\Intifact\Sdk\Model\SearchProductoSunat200Response**](../Model/SearchProductoSunat200Response.md)

### Authorization

[apiKey](../../README.md#apiKey)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
