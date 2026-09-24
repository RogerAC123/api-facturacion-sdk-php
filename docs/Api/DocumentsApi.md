# Intifact\Sdk\DocumentsApi

Consulta y gestión de documentos

All URIs are relative to http://localhost:3099, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**consultarCdr()**](DocumentsApi.md#consultarCdr) | **POST** /api/v1/cdr/consultar | Consultar el CDR de un comprobante en SUNAT por referencia |
| [**getDocument()**](DocumentsApi.md#getDocument) | **GET** /api/v1/documents/{id} | Detalle completo de un documento |
| [**getNextCorrelativo()**](DocumentsApi.md#getNextCorrelativo) | **GET** /api/v1/documents/next-correlativo | Obtener el siguiente correlativo disponible para una serie |
| [**listDocuments()**](DocumentsApi.md#listDocuments) | **GET** /api/v1/documents | Listar documentos con filtros y paginación |
| [**reconcileDocument()**](DocumentsApi.md#reconcileDocument) | **POST** /api/v1/documents/{id}/recover | Reconciliar un documento con SUNAT (consulta de CDR, solo master) |
| [**retryDocument()**](DocumentsApi.md#retryDocument) | **POST** /api/v1/documents/{id}/retry | Re-encolar un documento fallido |


## `consultarCdr()`

```php
consultarCdr($consultar_cdr_request): \Intifact\Sdk\Model\ConsultarCdr200Response
```

Consultar el CDR de un comprobante en SUNAT por referencia

Recupera el CDR oficial (billConsultService / getStatusCdr) de un comprobante 01/03/07/08 por RUC+serie+número, aunque no exista en esta BD. Útil para recuperar el histórico emitido por otro PSE. Solo en producción; usa la Clave SOL de la empresa (debe existir y estar en scope de la API key).

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: apiKey
$config = Intifact\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Intifact\Sdk\Api\DocumentsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$consultar_cdr_request = new \Intifact\Sdk\Model\ConsultarCdrRequest(); // \Intifact\Sdk\Model\ConsultarCdrRequest

try {
    $result = $apiInstance->consultarCdr($consultar_cdr_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DocumentsApi->consultarCdr: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **consultar_cdr_request** | [**\Intifact\Sdk\Model\ConsultarCdrRequest**](../Model/ConsultarCdrRequest.md)|  | |

### Return type

[**\Intifact\Sdk\Model\ConsultarCdr200Response**](../Model/ConsultarCdr200Response.md)

### Authorization

[apiKey](../../README.md#apiKey)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getDocument()`

```php
getDocument($id)
```

Detalle completo de un documento

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: apiKey
$config = Intifact\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Intifact\Sdk\Api\DocumentsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string

try {
    $apiInstance->getDocument($id);
} catch (Exception $e) {
    echo 'Exception when calling DocumentsApi->getDocument: ', $e->getMessage(), PHP_EOL;
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

## `getNextCorrelativo()`

```php
getNextCorrelativo($company_ruc, $tipo_doc, $serie): \Intifact\Sdk\Model\GetNextCorrelativo200Response
```

Obtener el siguiente correlativo disponible para una serie

Busca el correlativo más alto existente para la combinación empresa+tipoDoc+serie y retorna el siguiente. Útil para auto-numeración.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: apiKey
$config = Intifact\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Intifact\Sdk\Api\DocumentsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$company_ruc = 'company_ruc_example'; // string
$tipo_doc = 'tipo_doc_example'; // string
$serie = 'serie_example'; // string

try {
    $result = $apiInstance->getNextCorrelativo($company_ruc, $tipo_doc, $serie);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DocumentsApi->getNextCorrelativo: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **company_ruc** | **string**|  | |
| **tipo_doc** | **string**|  | |
| **serie** | **string**|  | |

### Return type

[**\Intifact\Sdk\Model\GetNextCorrelativo200Response**](../Model/GetNextCorrelativo200Response.md)

### Authorization

[apiKey](../../README.md#apiKey)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `listDocuments()`

```php
listDocuments($ruc, $tenant_id, $tipo_doc, $serie, $correlativo, $estado, $env, $fecha_desde, $fecha_hasta, $cliente_num_doc, $page, $limit): \Intifact\Sdk\Model\ListDocuments200Response
```

Listar documentos con filtros y paginación

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: apiKey
$config = Intifact\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Intifact\Sdk\Api\DocumentsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$ruc = 'ruc_example'; // string
$tenant_id = 'tenant_id_example'; // string
$tipo_doc = 'tipo_doc_example'; // string
$serie = 'serie_example'; // string
$correlativo = 'correlativo_example'; // string
$estado = 'estado_example'; // string
$env = 'env_example'; // string
$fecha_desde = 'fecha_desde_example'; // string
$fecha_hasta = 'fecha_hasta_example'; // string
$cliente_num_doc = 'cliente_num_doc_example'; // string
$page = 1; // int
$limit = 20; // int

try {
    $result = $apiInstance->listDocuments($ruc, $tenant_id, $tipo_doc, $serie, $correlativo, $estado, $env, $fecha_desde, $fecha_hasta, $cliente_num_doc, $page, $limit);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DocumentsApi->listDocuments: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **ruc** | **string**|  | [optional] |
| **tenant_id** | **string**|  | [optional] |
| **tipo_doc** | **string**|  | [optional] |
| **serie** | **string**|  | [optional] |
| **correlativo** | **string**|  | [optional] |
| **estado** | **string**|  | [optional] |
| **env** | **string**|  | [optional] |
| **fecha_desde** | **string**|  | [optional] |
| **fecha_hasta** | **string**|  | [optional] |
| **cliente_num_doc** | **string**|  | [optional] |
| **page** | **int**|  | [optional] [default to 1] |
| **limit** | **int**|  | [optional] [default to 20] |

### Return type

[**\Intifact\Sdk\Model\ListDocuments200Response**](../Model/ListDocuments200Response.md)

### Authorization

[apiKey](../../README.md#apiKey)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `reconcileDocument()`

```php
reconcileDocument($id): \Intifact\Sdk\Model\ReconcileDocument200Response
```

Reconciliar un documento con SUNAT (consulta de CDR, solo master)

Consulta el estado REAL en SUNAT (getStatusCdr / billConsultService) SIN reenviar y corrige la BD. Útil cuando un documento quedó desincronizado (ej. una boleta ACEPTADA figurando RECHAZADO/COLA_FALLIDA/ENCOLADO). Solo comprobantes 01/03/07/08, solo en producción. Restringido al master API key.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: apiKey
$config = Intifact\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Intifact\Sdk\Api\DocumentsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string

try {
    $result = $apiInstance->reconcileDocument($id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DocumentsApi->reconcileDocument: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**|  | |

### Return type

[**\Intifact\Sdk\Model\ReconcileDocument200Response**](../Model/ReconcileDocument200Response.md)

### Authorization

[apiKey](../../README.md#apiKey)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `retryDocument()`

```php
retryDocument($id): \Intifact\Sdk\Model\RetryDocument202Response
```

Re-encolar un documento fallido

Útil cuando un documento quedó en estado COLA_FALLIDA tras agotar los reintentos automáticos.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: apiKey
$config = Intifact\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Intifact\Sdk\Api\DocumentsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string

try {
    $result = $apiInstance->retryDocument($id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DocumentsApi->retryDocument: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**|  | |

### Return type

[**\Intifact\Sdk\Model\RetryDocument202Response**](../Model/RetryDocument202Response.md)

### Authorization

[apiKey](../../README.md#apiKey)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
