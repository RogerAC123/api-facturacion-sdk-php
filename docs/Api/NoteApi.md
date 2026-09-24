# Intifact\Sdk\NoteApi

Notas de Crédito/Débito (07, 08)

All URIs are relative to http://localhost:3099, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**computeNote()**](NoteApi.md#computeNote) | **POST** /api/v1/note/compute | Calcular importes (IGV, descuentos, totales) sin emitir |
| [**getNoteCdr()**](NoteApi.md#getNoteCdr) | **GET** /api/v1/note/{id}/cdr | Descargar CDR (constancia de SUNAT) |
| [**getNotePdf()**](NoteApi.md#getNotePdf) | **GET** /api/v1/note/{id}/pdf | Obtener PDF de la nota |
| [**getNoteXml()**](NoteApi.md#getNoteXml) | **GET** /api/v1/note/{id}/xml | Descargar XML firmado |
| [**sendNote()**](NoteApi.md#sendNote) | **POST** /api/v1/note/send | Enviar nota de crédito (07) o débito (08) a SUNAT |


## `computeNote()`

```php
computeNote($compute_invoice_request): \Intifact\Sdk\Model\ComputeInvoice200Response
```

Calcular importes (IGV, descuentos, totales) sin emitir

Motor de cálculo para notas: recibe ítems crudos (cantidad, valorUnitario sin IGV, afectación, descuento) y un descuento global opcional, y devuelve TODOS los importes fiscales calculados. No emite ni persiste nada — úsalo para previsualizar o para alimentar POST /note/send (agrega tú el documento afectado y el motivo).

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: apiKey
$config = Intifact\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Intifact\Sdk\Api\NoteApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$compute_invoice_request = new \Intifact\Sdk\Model\ComputeInvoiceRequest(); // \Intifact\Sdk\Model\ComputeInvoiceRequest

try {
    $result = $apiInstance->computeNote($compute_invoice_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling NoteApi->computeNote: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **compute_invoice_request** | [**\Intifact\Sdk\Model\ComputeInvoiceRequest**](../Model/ComputeInvoiceRequest.md)|  | |

### Return type

[**\Intifact\Sdk\Model\ComputeInvoice200Response**](../Model/ComputeInvoice200Response.md)

### Authorization

[apiKey](../../README.md#apiKey)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getNoteCdr()`

```php
getNoteCdr($id)
```

Descargar CDR (constancia de SUNAT)

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: apiKey
$config = Intifact\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Intifact\Sdk\Api\NoteApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string

try {
    $apiInstance->getNoteCdr($id);
} catch (Exception $e) {
    echo 'Exception when calling NoteApi->getNoteCdr: ', $e->getMessage(), PHP_EOL;
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

## `getNotePdf()`

```php
getNotePdf($id)
```

Obtener PDF de la nota

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: apiKey
$config = Intifact\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Intifact\Sdk\Api\NoteApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string

try {
    $apiInstance->getNotePdf($id);
} catch (Exception $e) {
    echo 'Exception when calling NoteApi->getNotePdf: ', $e->getMessage(), PHP_EOL;
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

## `getNoteXml()`

```php
getNoteXml($id)
```

Descargar XML firmado

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: apiKey
$config = Intifact\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Intifact\Sdk\Api\NoteApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string

try {
    $apiInstance->getNoteXml($id);
} catch (Exception $e) {
    echo 'Exception when calling NoteApi->getNoteXml: ', $e->getMessage(), PHP_EOL;
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

## `sendNote()`

```php
sendNote($send_note_request): \Intifact\Sdk\Model\SendInvoice202Response
```

Enviar nota de crédito (07) o débito (08) a SUNAT

Genera XML UBL 2.1, firma y encola. Responde 202. Consultar GET /documents/{id} para el resultado final. Idempotente por (RUC emisor, tipoDoc, serie, correlativo): reenviar el mismo comprobante NO lo duplica. Si ya fue aceptado devuelve el mismo id y hash sin reenviar nada a SUNAT; si sigue en proceso responde 409 (esperá el resultado, no cambies el correlativo). Solo un RECHAZADO exige un correlativo nuevo.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: apiKey
$config = Intifact\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Intifact\Sdk\Api\NoteApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$send_note_request = new \Intifact\Sdk\Model\SendNoteRequest(); // \Intifact\Sdk\Model\SendNoteRequest

try {
    $result = $apiInstance->sendNote($send_note_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling NoteApi->sendNote: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **send_note_request** | [**\Intifact\Sdk\Model\SendNoteRequest**](../Model/SendNoteRequest.md)|  | |

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
