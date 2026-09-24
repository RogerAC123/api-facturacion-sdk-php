# Intifact\Sdk\SummaryApi

Resumen Diario / Comunicación de Baja

All URIs are relative to http://localhost:3099, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**cancelBoleta()**](SummaryApi.md#cancelBoleta) | **POST** /api/v1/boleta/cancel | Anular boleta via resumen diario (estado&#x3D;3) |
| [**cancelInvoice()**](SummaryApi.md#cancelInvoice) | **POST** /api/v1/invoice/cancel | Anular factura via comunicación de baja |
| [**getTicketStatus()**](SummaryApi.md#getTicketStatus) | **GET** /api/v1/ticket/{ticket}/status | Consultar estado de ticket asíncrono (SOAP o GRE) |
| [**sendSummary()**](SummaryApi.md#sendSummary) | **POST** /api/v1/summary/send | Enviar resumen diario de boletas (RC) |
| [**sendVoided()**](SummaryApi.md#sendVoided) | **POST** /api/v1/voided/send | Enviar comunicación de baja (RA) |


## `cancelBoleta()`

```php
cancelBoleta($cancel_boleta_request): \Intifact\Sdk\Model\SendSummary202Response
```

Anular boleta via resumen diario (estado=3)

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: apiKey
$config = Intifact\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Intifact\Sdk\Api\SummaryApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$cancel_boleta_request = new \Intifact\Sdk\Model\CancelBoletaRequest(); // \Intifact\Sdk\Model\CancelBoletaRequest

try {
    $result = $apiInstance->cancelBoleta($cancel_boleta_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling SummaryApi->cancelBoleta: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **cancel_boleta_request** | [**\Intifact\Sdk\Model\CancelBoletaRequest**](../Model/CancelBoletaRequest.md)|  | |

### Return type

[**\Intifact\Sdk\Model\SendSummary202Response**](../Model/SendSummary202Response.md)

### Authorization

[apiKey](../../README.md#apiKey)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `cancelInvoice()`

```php
cancelInvoice($cancel_invoice_request): \Intifact\Sdk\Model\SendSummary202Response
```

Anular factura via comunicación de baja

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: apiKey
$config = Intifact\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Intifact\Sdk\Api\SummaryApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$cancel_invoice_request = new \Intifact\Sdk\Model\CancelInvoiceRequest(); // \Intifact\Sdk\Model\CancelInvoiceRequest

try {
    $result = $apiInstance->cancelInvoice($cancel_invoice_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling SummaryApi->cancelInvoice: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **cancel_invoice_request** | [**\Intifact\Sdk\Model\CancelInvoiceRequest**](../Model/CancelInvoiceRequest.md)|  | |

### Return type

[**\Intifact\Sdk\Model\SendSummary202Response**](../Model/SendSummary202Response.md)

### Authorization

[apiKey](../../README.md#apiKey)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getTicketStatus()`

```php
getTicketStatus($ruc, $ticket): \Intifact\Sdk\Model\GetTicketStatus200Response
```

Consultar estado de ticket asíncrono (SOAP o GRE)

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: apiKey
$config = Intifact\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Intifact\Sdk\Api\SummaryApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$ruc = 'ruc_example'; // string
$ticket = 'ticket_example'; // string

try {
    $result = $apiInstance->getTicketStatus($ruc, $ticket);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling SummaryApi->getTicketStatus: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **ruc** | **string**|  | |
| **ticket** | **string**|  | |

### Return type

[**\Intifact\Sdk\Model\GetTicketStatus200Response**](../Model/GetTicketStatus200Response.md)

### Authorization

[apiKey](../../README.md#apiKey)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `sendSummary()`

```php
sendSummary($send_summary_request): \Intifact\Sdk\Model\SendSummary202Response
```

Enviar resumen diario de boletas (RC)

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: apiKey
$config = Intifact\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Intifact\Sdk\Api\SummaryApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$send_summary_request = new \Intifact\Sdk\Model\SendSummaryRequest(); // \Intifact\Sdk\Model\SendSummaryRequest

try {
    $result = $apiInstance->sendSummary($send_summary_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling SummaryApi->sendSummary: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **send_summary_request** | [**\Intifact\Sdk\Model\SendSummaryRequest**](../Model/SendSummaryRequest.md)|  | |

### Return type

[**\Intifact\Sdk\Model\SendSummary202Response**](../Model/SendSummary202Response.md)

### Authorization

[apiKey](../../README.md#apiKey)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `sendVoided()`

```php
sendVoided($send_voided_request): \Intifact\Sdk\Model\SendSummary202Response
```

Enviar comunicación de baja (RA)

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: apiKey
$config = Intifact\Sdk\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Intifact\Sdk\Api\SummaryApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$send_voided_request = new \Intifact\Sdk\Model\SendVoidedRequest(); // \Intifact\Sdk\Model\SendVoidedRequest

try {
    $result = $apiInstance->sendVoided($send_voided_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling SummaryApi->sendVoided: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **send_voided_request** | [**\Intifact\Sdk\Model\SendVoidedRequest**](../Model/SendVoidedRequest.md)|  | |

### Return type

[**\Intifact\Sdk\Model\SendSummary202Response**](../Model/SendSummary202Response.md)

### Authorization

[apiKey](../../README.md#apiKey)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
