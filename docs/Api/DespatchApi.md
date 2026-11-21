# Intifact\Sdk\DespatchApi

Guías de Remisión (09 — GRE REST)

All URIs are relative to http://localhost:3000, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**getDespatchCdr()**](DespatchApi.md#getDespatchCdr) | **GET** /api/v1/despatch/{id}/cdr | Descargar CDR (constancia de SUNAT) |
| [**getDespatchPdf()**](DespatchApi.md#getDespatchPdf) | **GET** /api/v1/despatch/{id}/pdf | Obtener PDF de la guía (A4 oficina, ticket 80mm o 58mm POS) |
| [**getDespatchXml()**](DespatchApi.md#getDespatchXml) | **GET** /api/v1/despatch/{id}/xml | Descargar XML firmado de la guía |
| [**sendDespatch()**](DespatchApi.md#sendDespatch) | **POST** /api/v1/despatch/send | Enviar guía de remisión (09) via API GRE REST |
| [**sendDespatchMulti()**](DespatchApi.md#sendDespatchMulti) | **POST** /api/v1/despatch/send-multi | Enviar múltiples guías de remisión por destino |
| [**sendDespatchTransportista()**](DespatchApi.md#sendDespatchTransportista) | **POST** /api/v1/despatch-transportista/send | Enviar guía de remisión TRANSPORTISTA (31) via API GRE REST |


## `getDespatchCdr()`

```php
getDespatchCdr($id)
```

Descargar CDR (constancia de SUNAT)

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: apiKey
$config = Intifact\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Intifact\Sdk\Api\DespatchApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string

try {
    $apiInstance->getDespatchCdr($id);
} catch (Exception $e) {
    echo 'Exception when calling DespatchApi->getDespatchCdr: ', $e->getMessage(), PHP_EOL;
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

## `getDespatchPdf()`

```php
getDespatchPdf($id, $format)
```

Obtener PDF de la guía (A4 oficina, ticket 80mm o 58mm POS)

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: apiKey
$config = Intifact\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Intifact\Sdk\Api\DespatchApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string
$format = 'a4'; // string

try {
    $apiInstance->getDespatchPdf($id, $format);
} catch (Exception $e) {
    echo 'Exception when calling DespatchApi->getDespatchPdf: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**|  | |
| **format** | **string**|  | [optional] [default to &#39;a4&#39;] |

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

## `getDespatchXml()`

```php
getDespatchXml($id)
```

Descargar XML firmado de la guía

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: apiKey
$config = Intifact\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Intifact\Sdk\Api\DespatchApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string

try {
    $apiInstance->getDespatchXml($id);
} catch (Exception $e) {
    echo 'Exception when calling DespatchApi->getDespatchXml: ', $e->getMessage(), PHP_EOL;
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

## `sendDespatch()`

```php
sendDespatch($send_despatch_request): \Intifact\Sdk\Model\SendInvoice202Response
```

Enviar guía de remisión (09) via API GRE REST

Genera XML UBL 2.1, firma y encola. El worker obtiene token OAuth2, envía a SUNAT GRE, guarda ticket y luego hace polling de getStatus. Idempotente por (RUC emisor, tipoDoc, serie, correlativo): reenviar el mismo comprobante NO lo duplica. Si ya fue aceptado devuelve el mismo id y hash sin reenviar nada a SUNAT; si sigue en proceso responde 409 (esperá el resultado, no cambies el correlativo). Solo un RECHAZADO exige un correlativo nuevo.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: apiKey
$config = Intifact\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Intifact\Sdk\Api\DespatchApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$send_despatch_request = new \Intifact\Sdk\Model\SendDespatchRequest(); // \Intifact\Sdk\Model\SendDespatchRequest

try {
    $result = $apiInstance->sendDespatch($send_despatch_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DespatchApi->sendDespatch: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **send_despatch_request** | [**\Intifact\Sdk\Model\SendDespatchRequest**](../Model/SendDespatchRequest.md)|  | |

### Return type

[**\Intifact\Sdk\Model\SendInvoice202Response**](../Model/SendInvoice202Response.md)

### Authorization

[apiKey](../../README.md#apiKey)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `sendDespatchMulti()`

```php
sendDespatchMulti($send_despatch_multi_request): \Intifact\Sdk\Model\SendDespatchMulti202Response
```

Enviar múltiples guías de remisión por destino

Recibe datos comunes de transporte + array de destinos. Genera una guía por cada destino con correlativo auto-asignado. Cada guía se encola independientemente para envío a SUNAT GRE.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: apiKey
$config = Intifact\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Intifact\Sdk\Api\DespatchApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$send_despatch_multi_request = new \Intifact\Sdk\Model\SendDespatchMultiRequest(); // \Intifact\Sdk\Model\SendDespatchMultiRequest

try {
    $result = $apiInstance->sendDespatchMulti($send_despatch_multi_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DespatchApi->sendDespatchMulti: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **send_despatch_multi_request** | [**\Intifact\Sdk\Model\SendDespatchMultiRequest**](../Model/SendDespatchMultiRequest.md)|  | |

### Return type

[**\Intifact\Sdk\Model\SendDespatchMulti202Response**](../Model/SendDespatchMulti202Response.md)

### Authorization

[apiKey](../../README.md#apiKey)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `sendDespatchTransportista()`

```php
sendDespatchTransportista($send_despatch_transportista_request): \Intifact\Sdk\Model\SendInvoice202Response
```

Enviar guía de remisión TRANSPORTISTA (31) via API GRE REST

Guía emitida por la empresa de transporte (emisor=transportista). Incluye remitente (dueño de los bienes) y destinatario. Genera XML UBL 2.1, firma y encola para envío a SUNAT GRE.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: apiKey
$config = Intifact\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Intifact\Sdk\Api\DespatchApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$send_despatch_transportista_request = new \Intifact\Sdk\Model\SendDespatchTransportistaRequest(); // \Intifact\Sdk\Model\SendDespatchTransportistaRequest

try {
    $result = $apiInstance->sendDespatchTransportista($send_despatch_transportista_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DespatchApi->sendDespatchTransportista: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **send_despatch_transportista_request** | [**\Intifact\Sdk\Model\SendDespatchTransportistaRequest**](../Model/SendDespatchTransportistaRequest.md)|  | |

### Return type

[**\Intifact\Sdk\Model\SendInvoice202Response**](../Model/SendInvoice202Response.md)

### Authorization

[apiKey](../../README.md#apiKey)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
