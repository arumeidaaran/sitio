# 14. Tarjetas

Las tarjetas constituyen un patrón visual compartido por diferentes regiones del sitio.

Compartir el patrón no implica compartir un único contrato de datos.

---

## Estructura común

Conceptualmente:

```text
------------------------------------
| zona visual                      |
| -------------------------------- |
| contenido específico             |
| del tipo de elemento             |
|                                  |
| acción o enlace, si corresponde  |
------------------------------------
```

El lenguaje común comprende:

```text
tratamiento de superficie
borde
ausencia de redondeo por defecto
tipografía
espaciado
jerarquía
tratamiento de imagen o icono
tratamiento de enlaces
comportamiento entre temas
```

---

## Contenido específico

Cada tipo de tarjeta conserva sus propios campos.

No deben añadirse propiedades únicamente con el objetivo de hacer que dos tipos diferentes tengan el mismo contenido interno.

Conceptualmente:

```text
Contacto
=> icono
=> tipo de medio
=> enlace

Proyecto
=> imagen
=> nombre
=> descripción
=> Ver proyecto

Artículo
=> imagen
=> título
=> descripción
=> fecha de publicación
=> fecha de actualización
=> Leer artículo

Certificado
=> imagen
=> tipo
=> nombre
=> entidad
=> fecha
=> Ver certificado

Certificación
=> imagen
=> tipo
=> nombre
=> entidad
=> fecha
=> expiración
=> Ver certificación
```

---

## Rejilla

Las páginas de listado y las regiones destacadas que utilizan tarjetas presentan tantas tarjetas completas como permita el ancho disponible.

No se define:

```text
cantidad mínima fija de columnas
cantidad máxima fija de columnas
cantidad fijas de tarjetas por fila
```

La regla es:

```text
Tarjetas que caben correctamente
=> permanecen en la fila actual

Siguiente tarjeta ya no cabe correctamente
=> sigue en la fila siguiente
```

La cantidad de columnas constituye una consecuencia del espacio disponible y del tamaño efectivo del contenido.

El mínimo natural es una tarjeta por fila.

Conceptualmente:

```text
Si cabe uno
=> una tarjeta por fila

Si cabe más que uno
=> cuanto cabe de tarjeta por fila sin romper la tarjeta como elemento único
```

La cantidad total de elementos no constituye una restricción estructural del componente.

Esta regla se aplica a las rejillas de:

```text
Proyectos
Artículos
Certificaciones
Contactos
Contenido destacado
```

El aumento del texto debe reducir la cantidad de columnas cuando sea necesario antes de producir recorte, superposición o desplazamiento horizontal de la página.

---

## Altura y alineación

Las tarjetas pertenecientes a una misma rejilla deben mantener una composición visual coherente.

La estructura interna debe permitir que diferencias razonables de longitud de texto no destruyan la alineación general.

Cuando existe una acción explícita al final de la tarjeta, su posición debe permanecer visualmente consistente dentro de la rejilla.

La coherencia visual no establece una altura máxima que impida el crecimiento de una tarjeta cuando su contenido textual necesita más espacio.

---

## Interacción

La tarjeta completa nunca debe convertirse implícitamente en enlace, siempre habrá un enlace específico para la acción explícita.

En Contactos, el propio valor del medio constituye el enlace y no se añade una segunda acción redundante.

Cada acción independiente dentro de una tarjeta utiliza como mínimo:

```text
48px x 48px CSS
```

de área interactiva.

La superficie interactiva corresponde al enlace o control explícito y no se extiende artificialmente a toda la tarjeta.

El paso del puntero cambia el tratamiento visual del control o de la tarjeta como retroalimentación, pero no revela una función que no esté disponible sin ese estado.

---

## Resumen de rejillas

```text
Columnas
=> tantas tarjetas completas como permita el ancho disponible y el tamaño efectivo del contenido

Siguiente tarjeta no cabe
=> nueva fila

Mínimo natural
=> una tarjeta por fila
```

No existe una cantidad fija de columnas.

---

