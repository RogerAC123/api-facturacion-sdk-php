# Intifact\Sdk\SummaryApi

Resumen Diario / Comunicación de Baja

All URIs are relative to http://localhost:3000, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**apiV1BoletaCancelPost()**](SummaryApi.md#apiV1BoletaCancelPost) | **POST** /api/v1/boleta/cancel | Anular boleta via resumen diario (estado&#x3D;3) |
| [**apiV1InvoiceCancelPost()**](SummaryApi.md#apiV1InvoiceCancelPost) | **POST** /api/v1/invoice/cancel | Anular factura via comunicación de baja |
| [**apiV1SummarySendPost()**](SummaryApi.md#apiV1SummarySendPost) | **POST** /api/v1/summary/send | Enviar resumen diario de boletas (RC) |
| [**apiV1TicketTicketStatusGet()**](SummaryApi.md#apiV1TicketTicketStatusGet) | **GET** /api/v1/ticket/{ticket}/status | Consultar estado de ticket asíncrono (SOAP o GRE) |
| [**apiV1VoidedSendPost()**](SummaryApi.md#apiV1VoidedSendPost) | **POST** /api/v1/voided/send | Enviar comunicación de baja (RA) |


## `apiV1BoletaCancelPost()`

```php
apiV1BoletaCancelPost($api_v1_boleta_cancel_post_request): \Intifact\Sdk\Model\ApiV1SummarySendPost202Response
```

Anular boleta via resumen diario (estado=3)

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new Intifact\Sdk\Api\SummaryApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$api_v1_boleta_cancel_post_request = new \Intifact\Sdk\Model\ApiV1BoletaCancelPostRequest(); // \Intifact\Sdk\Model\ApiV1BoletaCancelPostRequest

try {
    $result = $apiInstance->apiV1BoletaCancelPost($api_v1_boleta_cancel_post_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling SummaryApi->apiV1BoletaCancelPost: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **api_v1_boleta_cancel_post_request** | [**\Intifact\Sdk\Model\ApiV1BoletaCancelPostRequest**](../Model/ApiV1BoletaCancelPostRequest.md)|  | |

### Return type

[**\Intifact\Sdk\Model\ApiV1SummarySendPost202Response**](../Model/ApiV1SummarySendPost202Response.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `apiV1InvoiceCancelPost()`

```php
apiV1InvoiceCancelPost($api_v1_invoice_cancel_post_request): \Intifact\Sdk\Model\ApiV1SummarySendPost202Response
```

Anular factura via comunicación de baja

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new Intifact\Sdk\Api\SummaryApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$api_v1_invoice_cancel_post_request = new \Intifact\Sdk\Model\ApiV1InvoiceCancelPostRequest(); // \Intifact\Sdk\Model\ApiV1InvoiceCancelPostRequest

try {
    $result = $apiInstance->apiV1InvoiceCancelPost($api_v1_invoice_cancel_post_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling SummaryApi->apiV1InvoiceCancelPost: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **api_v1_invoice_cancel_post_request** | [**\Intifact\Sdk\Model\ApiV1InvoiceCancelPostRequest**](../Model/ApiV1InvoiceCancelPostRequest.md)|  | |

### Return type

[**\Intifact\Sdk\Model\ApiV1SummarySendPost202Response**](../Model/ApiV1SummarySendPost202Response.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `apiV1SummarySendPost()`

```php
apiV1SummarySendPost($api_v1_summary_send_post_request): \Intifact\Sdk\Model\ApiV1SummarySendPost202Response
```

Enviar resumen diario de boletas (RC)

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new Intifact\Sdk\Api\SummaryApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$api_v1_summary_send_post_request = new \Intifact\Sdk\Model\ApiV1SummarySendPostRequest(); // \Intifact\Sdk\Model\ApiV1SummarySendPostRequest

try {
    $result = $apiInstance->apiV1SummarySendPost($api_v1_summary_send_post_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling SummaryApi->apiV1SummarySendPost: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **api_v1_summary_send_post_request** | [**\Intifact\Sdk\Model\ApiV1SummarySendPostRequest**](../Model/ApiV1SummarySendPostRequest.md)|  | |

### Return type

[**\Intifact\Sdk\Model\ApiV1SummarySendPost202Response**](../Model/ApiV1SummarySendPost202Response.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `apiV1TicketTicketStatusGet()`

```php
apiV1TicketTicketStatusGet($ruc, $ticket): \Intifact\Sdk\Model\ApiV1TicketTicketStatusGet200Response
```

Consultar estado de ticket asíncrono (SOAP o GRE)

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new Intifact\Sdk\Api\SummaryApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$ruc = 'ruc_example'; // string
$ticket = 'ticket_example'; // string

try {
    $result = $apiInstance->apiV1TicketTicketStatusGet($ruc, $ticket);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling SummaryApi->apiV1TicketTicketStatusGet: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **ruc** | **string**|  | |
| **ticket** | **string**|  | |

### Return type

[**\Intifact\Sdk\Model\ApiV1TicketTicketStatusGet200Response**](../Model/ApiV1TicketTicketStatusGet200Response.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `apiV1VoidedSendPost()`

```php
apiV1VoidedSendPost($api_v1_voided_send_post_request): \Intifact\Sdk\Model\ApiV1SummarySendPost202Response
```

Enviar comunicación de baja (RA)

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new Intifact\Sdk\Api\SummaryApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$api_v1_voided_send_post_request = new \Intifact\Sdk\Model\ApiV1VoidedSendPostRequest(); // \Intifact\Sdk\Model\ApiV1VoidedSendPostRequest

try {
    $result = $apiInstance->apiV1VoidedSendPost($api_v1_voided_send_post_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling SummaryApi->apiV1VoidedSendPost: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **api_v1_voided_send_post_request** | [**\Intifact\Sdk\Model\ApiV1VoidedSendPostRequest**](../Model/ApiV1VoidedSendPostRequest.md)|  | |

### Return type

[**\Intifact\Sdk\Model\ApiV1SummarySendPost202Response**](../Model/ApiV1SummarySendPost202Response.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
