# 09. Certificaciones

La sección visible sigue denominándose:

```text
Certificaciones
```

y agrupa dos tipos de elementos:

```text
Certificado
Certificación
```

Los dos tipos pertenecen a la misma sección pero se identifican explícitamente.

---

## Listado

El listado utiliza la rejilla general de tarjetas.

Cada elemento incluye una indicación visible de su tipo.

---

## Certificado

Una tarjeta de certificado utiliza:

```text
------------------------------------
| imagen                           |
| -------------------------------- |
| Certificado                      |
| Nombre                           |
| Entidad                          |
| Fecha                            |
| Ver certificado                  |
------------------------------------
```

`Certificado` identifica visualmente el tipo de elemento.

No dispone de una línea artificial de expiración.

---

## Certificación

Una tarjeta de certificación utiliza:

```text
------------------------------------
| imagen                           |
| -------------------------------- |
| Certificación                    |
| Nombre                           |
| Entidad                          |
| Fecha                            |
| Expiración                       |
| Ver certificación                |
------------------------------------
```

`Certificación` identifica visualmente el tipo de elemento.

La línea de expiración forma parte de la estructura de esta tarjeta.

Cuando la certificación no expira, debe permanecer la línea y utilizar una representación localizada equivalente a:

```text
Expiración: No expira
```

No debe representarse:

```text
null
```

ni dejar un hueco sin contenido.

---

## Diferencia gráfica entre tipos

Certificado y Certificación deben presentar diferencias internas porque representan elementos distintos.

Esta diferencia no rompe la identidad visual general.

Ambos conservan:

```text
misma familia de tarjeta
misma geometría general
mismo tratamiento de imagen
mismos bordes
misma tipografía
mismo sistema de espaciado
misma jerarquía general
mismo comportamiento entre temas
```

El tipo visible permite reconocer la diferencia sin depender de la existencia o ausencia de determinados campos.

---

## Detalle

Al seleccionar un elemento, la región `Contenido` completa representa el elemento.

El detalle de un certificado presenta los datos correspondientes a su propio tipo.

El detalle de una certificación presenta además la información propia de la credencial.

Cuando una certificación no dispone de código o enlace de verificación, el espacio correspondiente utiliza un texto localizado equivalente a:

```text
No disponible
```

No se muestra `null` como contenido visible.

El detalle no incorpora una sección adicional de conocimientos relacionados.

---

## Adaptación responsive del detalle

En escritorio debe mantenerse una composición horizontal mientras el espacio disponible permita representar correctamente sus regiones.

Cuando el espacio disponible deja de permitir esta composición, incluido el crecimiento provocado por el redimensionamiento del texto, el detalle se reorganiza verticalmente.

Para una certificación, el orden conceptual es:

```text
Imagen
Certificación
Nombre
Entidad
Fecha
Expiración
Código de credencial
Enlace de verificación
Volver a certificaciones
```

Cada bloque utiliza el ancho disponible.

La imagen se redimensiona proporcionalmente.

Los valores definidos por el contrato se conservan.

En particular:

```text
Sin fecha de expiración
=> No expira

Credencial no disponible
=> No disponible
```

Un certificado utiliza la misma lógica responsive, pero no incorpora campos propios de una certificación que no pertenezcan a su tipo.

Las acciones de verificación y regreso que constituyen objetivos independientes aplican el tamaño mínimo general de interacción.

---

