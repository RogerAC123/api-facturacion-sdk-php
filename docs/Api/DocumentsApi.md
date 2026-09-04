# Intifact\Sdk\DocumentsApi

Consulta y gestión de documentos

All URIs are relative to http://localhost:3000, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**apiV1CdrConsultarPost()**](DocumentsApi.md#apiV1CdrConsultarPost) | **POST** /api/v1/cdr/consultar | Consultar el CDR de un comprobante en SUNAT por referencia |
| [**apiV1DocumentsGet()**](DocumentsApi.md#apiV1DocumentsGet) | **GET** /api/v1/documents | Listar documentos con filtros y paginación |
| [**apiV1DocumentsIdGet()**](DocumentsApi.md#apiV1DocumentsIdGet) | **GET** /api/v1/documents/{id} | Detalle completo de un documento |
| [**apiV1DocumentsIdRecoverPost()**](DocumentsApi.md#apiV1DocumentsIdRecoverPost) | **POST** /api/v1/documents/{id}/recover | Reconciliar un documento con SUNAT (consulta de CDR, solo master) |
| [**apiV1DocumentsIdRetryPost()**](DocumentsApi.md#apiV1DocumentsIdRetryPost) | **POST** /api/v1/documents/{id}/retry | Re-encolar un documento fallido |
| [**apiV1DocumentsNextCorrelativoGet()**](DocumentsApi.md#apiV1DocumentsNextCorrelativoGet) | **GET** /api/v1/documents/next-correlativo | Obtener el siguiente correlativo disponible para una serie |


## `apiV1CdrConsultarPost()`

```php
apiV1CdrConsultarPost($api_v1_cdr_consultar_post_request): \Intifact\Sdk\Model\ApiV1CdrConsultarPost200Response
```

Consultar el CDR de un comprobante en SUNAT por referencia

Recupera el CDR oficial (billConsultService / getStatusCdr) de un comprobante 01/03/07/08 por RUC+serie+número, aunque no exista en esta BD. Útil para recuperar el histórico emitido por otro PSE. Solo en producción; usa la Clave SOL de la empresa (debe existir y estar en scope de la API key).

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new Intifact\Sdk\Api\DocumentsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$api_v1_cdr_consultar_post_request = new \Intifact\Sdk\Model\ApiV1CdrConsultarPostRequest(); // \Intifact\Sdk\Model\ApiV1CdrConsultarPostRequest

try {
    $result = $apiInstance->apiV1CdrConsultarPost($api_v1_cdr_consultar_post_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DocumentsApi->apiV1CdrConsultarPost: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **api_v1_cdr_consultar_post_request** | [**\Intifact\Sdk\Model\ApiV1CdrConsultarPostRequest**](../Model/ApiV1CdrConsultarPostRequest.md)|  | |

### Return type

[**\Intifact\Sdk\Model\ApiV1CdrConsultarPost200Response**](../Model/ApiV1CdrConsultarPost200Response.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `apiV1DocumentsGet()`

```php
apiV1DocumentsGet($ruc, $tipo_doc, $serie, $estado, $env, $fecha_desde, $fecha_hasta, $cliente_num_doc, $page, $limit): \Intifact\Sdk\Model\ApiV1DocumentsGet200Response
```

Listar documentos con filtros y paginación

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new Intifact\Sdk\Api\DocumentsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$ruc = 'ruc_example'; // string
$tipo_doc = 'tipo_doc_example'; // string
$serie = 'serie_example'; // string
$estado = 'estado_example'; // string
$env = 'env_example'; // string
$fecha_desde = 'fecha_desde_example'; // string
$fecha_hasta = 'fecha_hasta_example'; // string
$cliente_num_doc = 'cliente_num_doc_example'; // string
$page = 1; // int
$limit = 20; // int

try {
    $result = $apiInstance->apiV1DocumentsGet($ruc, $tipo_doc, $serie, $estado, $env, $fecha_desde, $fecha_hasta, $cliente_num_doc, $page, $limit);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DocumentsApi->apiV1DocumentsGet: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **ruc** | **string**|  | [optional] |
| **tipo_doc** | **string**|  | [optional] |
| **serie** | **string**|  | [optional] |
| **estado** | **string**|  | [optional] |
| **env** | **string**|  | [optional] |
| **fecha_desde** | **string**|  | [optional] |
| **fecha_hasta** | **string**|  | [optional] |
| **cliente_num_doc** | **string**|  | [optional] |
| **page** | **int**|  | [optional] [default to 1] |
| **limit** | **int**|  | [optional] [default to 20] |

### Return type

[**\Intifact\Sdk\Model\ApiV1DocumentsGet200Response**](../Model/ApiV1DocumentsGet200Response.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `apiV1DocumentsIdGet()`

```php
apiV1DocumentsIdGet($id)
```

Detalle completo de un documento

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new Intifact\Sdk\Api\DocumentsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$id = 'id_example'; // string

try {
    $apiInstance->apiV1DocumentsIdGet($id);
} catch (Exception $e) {
    echo 'Exception when calling DocumentsApi->apiV1DocumentsIdGet: ', $e->getMessage(), PHP_EOL;
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

## `apiV1DocumentsIdRecoverPost()`

```php
apiV1DocumentsIdRecoverPost($id): \Intifact\Sdk\Model\ApiV1DocumentsIdRecoverPost200Response
```

Reconciliar un documento con SUNAT (consulta de CDR, solo master)

Consulta el estado REAL en SUNAT (getStatusCdr / billConsultService) SIN reenviar y corrige la BD. Útil cuando un documento quedó desincronizado (ej. una boleta ACEPTADA figurando RECHAZADO/COLA_FALLIDA/ENCOLADO). Solo comprobantes 01/03/07/08, solo en producción. Restringido al master API key.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new Intifact\Sdk\Api\DocumentsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$id = 'id_example'; // string

try {
    $result = $apiInstance->apiV1DocumentsIdRecoverPost($id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DocumentsApi->apiV1DocumentsIdRecoverPost: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**|  | |

### Return type

[**\Intifact\Sdk\Model\ApiV1DocumentsIdRecoverPost200Response**](../Model/ApiV1DocumentsIdRecoverPost200Response.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `apiV1DocumentsIdRetryPost()`

```php
apiV1DocumentsIdRetryPost($id): \Intifact\Sdk\Model\ApiV1DocumentsIdRetryPost202Response
```

Re-encolar un documento fallido

Útil cuando un documento quedó en estado COLA_FALLIDA tras agotar los reintentos automáticos.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new Intifact\Sdk\Api\DocumentsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$id = 'id_example'; // string

try {
    $result = $apiInstance->apiV1DocumentsIdRetryPost($id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DocumentsApi->apiV1DocumentsIdRetryPost: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**|  | |

### Return type

[**\Intifact\Sdk\Model\ApiV1DocumentsIdRetryPost202Response**](../Model/ApiV1DocumentsIdRetryPost202Response.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `apiV1DocumentsNextCorrelativoGet()`

```php
apiV1DocumentsNextCorrelativoGet($company_ruc, $tipo_doc, $serie): \Intifact\Sdk\Model\ApiV1DocumentsNextCorrelativoGet200Response
```

Obtener el siguiente correlativo disponible para una serie

Busca el correlativo más alto existente para la combinación empresa+tipoDoc+serie y retorna el siguiente. Útil para auto-numeración.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new Intifact\Sdk\Api\DocumentsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$company_ruc = 'company_ruc_example'; // string
$tipo_doc = 'tipo_doc_example'; // string
$serie = 'serie_example'; // string

try {
    $result = $apiInstance->apiV1DocumentsNextCorrelativoGet($company_ruc, $tipo_doc, $serie);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DocumentsApi->apiV1DocumentsNextCorrelativoGet: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **company_ruc** | **string**|  | |
| **tipo_doc** | **string**|  | |
| **serie** | **string**|  | |

### Return type

[**\Intifact\Sdk\Model\ApiV1DocumentsNextCorrelativoGet200Response**](../Model/ApiV1DocumentsNextCorrelativoGet200Response.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
