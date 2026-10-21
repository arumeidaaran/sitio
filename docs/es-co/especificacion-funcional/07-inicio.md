# 07. Inicio

La página inicial presenta la identidad del sitio, una selección editorial de contenido y la actividad reciente.

Conceptualmente:

```text
Inicio
|
+-- Cabecera
|
+-- Contenido principal
|   |
|   +-- Proyectos destacados
|   |
|   +-- Artículos destacados
|   |
|   +-- Certificaciones destacadas
|
+-- Actualizaciones
```

No existe una segunda sección introductoria después de la cabecera.

La cabecera ya presenta:

```text
Nombre
Descripción breve
Identidad visual
```

Por ese motivo, Inicio no repite esta información mediante una presentación adicional ni mediante accesos redundantes hacia secciones ya disponibles en la navegación y en el propio contenido de la página.

## Proyectos destacados

La sección presenta proyectos seleccionados editorialmente para recibir mayor visibilidad.

Cada elemento presenta:

```text
Imagen
Nombre
Descripción
Enlace explícito
```

El enlace conduce a la página del proyecto.

La tarjeta completa no constituye implícitamente un enlace.

Los lenguajes y sus porcentajes no forman parte de la tarjeta de Inicio.

La cantidad no constituye una limitación estructural del componente.

Al final de la sección se presenta:

```text
Ver todos los proyectos
```

## Artículos destacados

La sección presenta artículos seleccionados editorialmente.

Cada elemento presenta:

```text
Imagen
Título
Descripción
Fecha
Enlace explícito
```

No se requiere una categoría para representar el artículo.

El enlace conduce a la página del artículo.

La cantidad no constituye una limitación estructural del componente.

Al final de la sección se presenta:

```text
Ver todos los artículos
```

## Certificaciones destacadas

La sección presenta elementos seleccionados editorialmente dentro de Certificaciones.

Estos elementos deben corresponder a:

```text
Certificado
Certificación
```

Cada elemento presenta la información resumida necesaria para identificar el elemento y acceder a su detalle.

La cantidad no constituye una limitación estructural del componente.

Al final de la sección se presenta:

```text
Ver todas las certificaciones
```

## Destacados

La condición de destacado constituye una decisión editorial sobre un elemento.

Conceptualmente:

```text
Recurso
|
+-- destacado
|   |
|   +-- sí
|   |   => debe aparecer en Inicio
|   |
|   +-- no
|       => no forma parte de la selección destacada
|
+-- orden editorial
    => determina su posición entre los destacados
```

La selección editorial y la recuperación de los datos constituyen responsabilidades diferentes.

```text
Selección del contenido destacado
=> decisión editorial

Filtrado y orden
=> sitio-api

Representación
=> sitio
```

La selección destacada no depende necesariamente de la fecha de publicación, importancia automática ni otro criterio implícito.

Los elementos deben ser seleccionados y ordenados deliberadamente.

## Actualizaciones

El área de exposición de Inicio presenta novedades y contenido reciente.

Conceptualmente:

```text
Actualizaciones

Novedades y contenido reciente

[actualización]
[actualización]
...
```

Esta región debe contener actividad relacionada con:

```text
Proyecto
Artículo
Certificado
Certificación
```

Los acontecimientos representados corresponden a:

```text
Contenido nuevo

Contenido actualizado
```

Cada actualización presenta:

```text
Ícono
Tipo de acontecimiento
Nombre
Descripción
Fecha
Enlace explícito
```

El tipo de acción del enlace depende del elemento.

Conceptualmente:

```text
Proyecto
=> Ver proyecto

Artículo
=> Leer artículo

Certificado
=> Ver certificado

Certificación
=> Ver certificación
```

Las actualizaciones se ordenan de acuerdo con la fecha de actividad, desde la más reciente hacia la menos reciente.

No existe un período temporal fijo para determinar qué contenido debe aparecer.

Conceptualmente:

```text
Reciente
=> forma parte de la actividad más reciente disponible

No significa
=> ocurrió necesariamente dentro de un período predeterminado
```

Los destacados y las actualizaciones constituyen dimensiones diferentes del contenido.

```text
Destacados
=> qué contenido se desea poner en evidencia

Actualizaciones
=> qué contenido tuvo actividad más recientemente
```

Un mismo elemento debe pertenecer simultáneamente a ambas regiones.

