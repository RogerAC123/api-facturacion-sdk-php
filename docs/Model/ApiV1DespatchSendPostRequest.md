# ApiV1DespatchSendPostRequest

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
**cliente_tipo_doc** | **string** |  |
**cliente_num_doc** | **string** |  |
**cliente_razon_social** | **string** |  |
**cliente_direccion** | **string** |  | [optional]
**cliente_distrito** | **string** |  | [optional]
**cliente_provincia** | **string** |  | [optional]
**cliente_departamento** | **string** |  | [optional]
**destinatario_contacto** | **string** |  | [optional]
**destinatario_telefono** | **string** |  | [optional]
**destinatario_email** | **string** |  | [optional]
**entrega_referencia** | **string** |  | [optional]
**modalidad_entrega** | **string** |  | [optional]
**agencia_nombre** | **string** |  | [optional]
**agencia_sede** | **string** |  | [optional]
**guia_cod_traslado** | **string** |  |
**guia_mod_traslado** | **string** |  |
**guia_peso_total** | **float** |  |
**guia_und_peso_total** | **string** |  | [optional] [default to 'KGM']
**guia_fec_traslado** | **string** |  |
**guia_vehiculo_placa** | **string** |  | [optional]
**transportista_tipo_doc** | **string** |  | [optional]
**transportista_num_doc** | **string** |  | [optional]
**transportista_razon_social** | **string** |  | [optional]
**transportista_nro_mtc** | **string** |  | [optional]
**guia_partida_ubigeo** | **string** |  |
**guia_partida_direccion** | **string** |  |
**guia_partida_ciudad** | **string** |  | [optional]
**guia_llegada_ubigeo** | **string** |  |
**guia_llegada_direccion** | **string** |  |
**guia_llegada_ciudad** | **string** |  | [optional]
**chofer** | [**\Intifact\Sdk\Model\ApiV1DespatchSendPostRequestChoferInner[]**](ApiV1DespatchSendPostRequestChoferInner.md) |  | [optional]
**guia_fec_entrega** | **string** |  | [optional]
**guia_des_traslado** | **string** |  | [optional]
**guia_peso_neto** | **float** |  | [optional]
**guia_sustento_peso** | **string** |  | [optional]
**guia_num_bultos** | **int** |  | [optional]
**indicadores** | [**\Intifact\Sdk\Model\ApiV1DespatchSendPostRequestIndicadores**](ApiV1DespatchSendPostRequestIndicadores.md) |  | [optional]
**contenedores** | [**\Intifact\Sdk\Model\ApiV1DespatchSendPostRequestContenedoresInner[]**](ApiV1DespatchSendPostRequestContenedoresInner.md) |  | [optional]
**guia_vehiculo_tuc** | **string** |  | [optional]
**guia_vehiculo_autorizacion** | **string** |  | [optional]
**guia_vehiculo_autorizacion_entidad** | **string** |  | [optional]
**vehiculos_secundarios** | [**\Intifact\Sdk\Model\ApiV1DespatchSendPostRequestVehiculosSecundariosInner[]**](ApiV1DespatchSendPostRequestVehiculosSecundariosInner.md) |  | [optional]
**transportista_autorizacion** | **string** |  | [optional]
**transportista_autorizacion_entidad** | **string** |  | [optional]
**guia_partida_ruc** | **string** |  | [optional]
**guia_partida_cod_local** | **string** |  | [optional]
**guia_partida_geo** | [**\Intifact\Sdk\Model\ApiV1DespatchSendPostRequestGuiaPartidaGeo**](ApiV1DespatchSendPostRequestGuiaPartidaGeo.md) |  | [optional]
**guia_llegada_ruc** | **string** |  | [optional]
**guia_llegada_cod_local** | **string** |  | [optional]
**guia_llegada_geo** | [**\Intifact\Sdk\Model\ApiV1DespatchSendPostRequestGuiaLlegadaGeo**](ApiV1DespatchSendPostRequestGuiaLlegadaGeo.md) |  | [optional]
**documentos_relacionados** | [**\Intifact\Sdk\Model\ApiV1DespatchSendPostRequestDocumentosRelacionadosInner[]**](ApiV1DespatchSendPostRequestDocumentosRelacionadosInner.md) |  | [optional]
**remitente_autorizacion** | **string** |  | [optional]
**remitente_autorizacion_entidad** | **string** |  | [optional]
**proveedor_tipo_doc** | **string** |  | [optional]
**proveedor_num_doc** | **string** |  | [optional]
**proveedor_razon_social** | **string** |  | [optional]
**comprador_tipo_doc** | **string** |  | [optional]
**comprador_num_doc** | **string** |  | [optional]
**comprador_razon_social** | **string** |  | [optional]
**puerto_codigo** | **string** |  | [optional]
**puerto_nombre** | **string** |  | [optional]
**puerto_tipo** | **string** |  | [optional]
**detalle** | [**\Intifact\Sdk\Model\ApiV1DespatchSendPostRequestDetalleInner[]**](ApiV1DespatchSendPostRequestDetalleInner.md) |  |

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
