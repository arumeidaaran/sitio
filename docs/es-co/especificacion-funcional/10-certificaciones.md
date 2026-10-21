# 10. Certificaciones

La sección denominada `Certificaciones` reúne dos tipos de elementos:

```text
Certificado
Certificación
```

Un certificado representa principalmente un comprobante de realización o finalización de una actividad, curso o formación.

Una certificación representa una credencial obtenida mediante un proceso de certificación y debe incorporar datos adicionales relacionados con su vigencia y verificación.

La sección utiliza una rejilla de tarjetas.

Conceptualmente:

```text
+-----------------+ +-----------------+ +-----------------+ 
|   certificado   | |   certificado   | |  certificacion  | 
+-----------------+ +-----------------+ +-----------------+ 

+-----------------+ +-----------------+ +-----------------+ 
|  certificacion  | |   certificado   | |  certificacion  | 
+-----------------+ +-----------------+ +-----------------+ 
```

Las tarjetas se distribuyen horizontalmente de acuerdo con el espacio disponible y continúan en una nueva fila cuando la siguiente tarjeta ya no debe presentarse correctamente en la misma línea.

La cantidad de tarjetas por fila no constituye una propiedad fija del listado.

No hay orden de precedencia entre un certificado y una certificación puramente. El orden para sus apariciones mediante es sus fechas.

## Tarjeta de certificado

Conceptualmente:

```text
--------------------------------
| imagen                       |
| ---------------------------- |
| Certificado                  |
| Nombre                       |
| Entidad                      |
| Fecha                        |
| Ver certificado              |
--------------------------------
```

## Tarjeta de certificación

Conceptualmente:

```text
--------------------------------
| imagen                       |
| ---------------------------- |
| Certificación                |
| Nombre                       |
| Entidad                      |
| Fecha                        |
| Expiración                   |
| Ver certificación            |
--------------------------------
```

El tipo constituye información visible.

Los valores técnicos del contrato son localizados por el frontend.

Conceptualmente:

```text
certificate
=> Certificado

certification
=> Certificación
```

Cuando una certificación no dispone de fecha de expiración, la tarjeta conserva el espacio correspondiente y presenta una representación localizada equivalente a:

```text
Expiración: No expira
```

No se representa `null` directamente al usuario.

Los campos propios de una certificación que no se aplican a un certificado no pertenecen al contrato de certificado.

El listado completo se ordena por fecha de emisión desde la más reciente hacia la más antigua.

## Detalle

Al seleccionar un certificado o una certificación, toda la región `Contenido` pasa a representar el elemento seleccionado.

Su contenido viene del backend.

Los datos disponen de una estructura definida por su contrato.

Cuando una certificación carece de código o enlace de verificación, el lugar correspondiente se representa mediante un texto localizado equivalente a:

```text
No disponible
```

El frontend no presenta valores técnicos `null`.

