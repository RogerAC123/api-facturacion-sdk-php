# ApiV1DespatchTransportistaSendPostRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**tipo_doc** | **string** |  |
**serie** | **string** |  |
**correlativo** | **string** |  |
**observacion** | **string** |  | [optional]
**fecha_emision** | **string** |  |
**empresa_ruc** | **string** |  |
**establecimiento_codigo** | **string** |  | [optional] [default to '0000']
**transportista_nro_mtc** | **string** |  | [optional]
**destinatario_tipo_doc** | **string** |  |
**destinatario_num_doc** | **string** |  |
**destinatario_razon_social** | **string** |  |
**destinatario_direccion** | **string** |  | [optional]
**destinatario_distrito** | **string** |  | [optional]
**destinatario_provincia** | **string** |  | [optional]
**destinatario_departamento** | **string** |  | [optional]
**destinatario_contacto** | **string** |  | [optional]
**destinatario_telefono** | **string** |  | [optional]
**destinatario_email** | **string** |  | [optional]
**entrega_referencia** | **string** |  | [optional]
**modalidad_entrega** | **string** |  | [optional]
**agencia_nombre** | **string** |  | [optional]
**agencia_sede** | **string** |  | [optional]
**remitente_tipo_doc** | **string** |  |
**remitente_num_doc** | **string** |  |
**remitente_razon_social** | **string** |  |
**guia_cod_traslado** | **string** |  |
**guia_des_traslado** | **string** |  | [optional]
**guia_peso_total** | **float** |  |
**guia_und_peso_total** | **string** |  | [optional] [default to 'KGM']
**guia_num_bultos** | **int** |  | [optional]
**guia_fec_traslado** | **string** |  |
**chofer** | [**\Intifact\Sdk\Model\ApiV1DespatchSendPostRequestChoferInner[]**](ApiV1DespatchSendPostRequestChoferInner.md) |  |
**guia_vehiculo_placa** | **string** |  |
**guia_vehiculo_tuc** | **string** |  | [optional]
**vehiculos_secundarios** | [**\Intifact\Sdk\Model\ApiV1DespatchTransportistaSendPostRequestVehiculosSecundariosInner[]**](ApiV1DespatchTransportistaSendPostRequestVehiculosSecundariosInner.md) |  | [optional]
**guia_partida_ubigeo** | **string** |  |
**guia_partida_direccion** | **string** |  |
**guia_llegada_ubigeo** | **string** |  |
**guia_llegada_direccion** | **string** |  |
**documentos_relacionados** | [**\Intifact\Sdk\Model\ApiV1DespatchSendPostRequestDocumentosRelacionadosInner[]**](ApiV1DespatchSendPostRequestDocumentosRelacionadosInner.md) |  | [optional]
**detalle** | [**\Intifact\Sdk\Model\ApiV1DespatchSendPostRequestDetalleInner[]**](ApiV1DespatchSendPostRequestDetalleInner.md) |  |

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
