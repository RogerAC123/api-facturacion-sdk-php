# ApiV1InvoiceSendPostRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**tipo_operacion** | **string** |  | [optional] [default to '0101']
**tipo_doc** | **string** |  |
**serie** | **string** |  |
**correlativo** | **string** |  |
**tipo_moneda** | **string** |  | [optional] [default to 'PEN']
**fecha_emision** | **string** |  |
**empresa_ruc** | **string** |  |
**establecimiento_codigo** | **string** |  | [optional] [default to '0000']
**cliente_tipo_doc** | **string** |  |
**cliente_num_doc** | **string** |  |
**cliente_razon_social** | **string** |  |
**cliente_direccion** | **string** |  | [optional]
**cliente_distrito** | **string** |  | [optional]
**cliente_provincia** | **string** |  | [optional]
**cliente_departamento** | **string** |  | [optional]
**monto_oper_gravadas** | **float** |  | [optional] [default to 0]
**monto_oper_exoneradas** | **float** |  | [optional] [default to 0]
**monto_oper_inafectas** | **float** |  | [optional] [default to 0]
**monto_oper_gratuitas** | **float** |  | [optional] [default to 0]
**monto_igv** | **float** |  |
**total_impuestos** | **float** |  |
**valor_venta** | **float** |  |
**sub_total** | **float** |  |
**monto_imp_venta** | **float** |  |
**descuento_global** | **float** |  | [optional]
**descuento_global_base** | **float** |  | [optional]
**detalle** | [**\Intifact\Sdk\Model\ApiV1InvoiceSendPostRequestDetalleInner[]**](ApiV1InvoiceSendPostRequestDetalleInner.md) |  |
**forma_pago** | [**\Intifact\Sdk\Model\ApiV1InvoiceSendPostRequestFormaPagoInner[]**](ApiV1InvoiceSendPostRequestFormaPagoInner.md) |  |
**leyendas** | [**\Intifact\Sdk\Model\ApiV1InvoiceSendPostRequestLeyendasInner[]**](ApiV1InvoiceSendPostRequestLeyendasInner.md) |  |
**observacion** | **string** |  | [optional]
**vendedor** | **string** |  | [optional]
**pagos** | [**\Intifact\Sdk\Model\ApiV1InvoiceSendPostRequestPagosInner[]**](ApiV1InvoiceSendPostRequestPagosInner.md) |  | [optional]
**detraccion** | [**\Intifact\Sdk\Model\ApiV1InvoiceSendPostRequestDetraccion**](ApiV1InvoiceSendPostRequestDetraccion.md) |  | [optional]
**guia_remision** | [**\Intifact\Sdk\Model\ApiV1InvoiceSendPostRequestGuiaRemisionInner[]**](ApiV1InvoiceSendPostRequestGuiaRemisionInner.md) |  | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
