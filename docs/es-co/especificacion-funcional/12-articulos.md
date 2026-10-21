# 12. Artículos

Volver al índice [aquí](../README.md#índice).

La página de Artículos utiliza una rejilla de tarjetas.

Cada tarjeta presenta:

```text
Imagen
Título
Descripción breve
Fecha de publicación
Fecha de actualización
Leer artículo
```

Todas las tarjetas mantienen ambos espacios de fecha.

`publication_date` representa la fecha original de publicación.

`update_date` representa la fecha de la última versión publicada.

Cuando un artículo todavía no ha recibido un cambio posterior:

```text
publication_date
=> fecha de creación

update_date
=> misma fecha
```

Después de una actualización:

```text
publication_date
=> permanece

update_date
=> fecha de la nueva versión
```

Por lo tanto:

```text
update_date >= publication_date
```

`update_date` no utiliza `null`.

El listado completo de artículos se ordena mediante `publication_date` desde la fecha más reciente hacia la más antigua.

## Artículo

Al seleccionar `Leer artículo`, toda la región `Contenido` pasa a representar el artículo.

Los artículos constituyen el contenido cuya fuente editorial utiliza Markdown, pero se ubican mediante información que viene del backend.

Conceptualmente:

```text
Archivo Markdown
|
+-- Metadatos
|
+-- Cuerpo del artículo
```

El cuerpo debe variar libremente de acuerdo con las necesidades del artículo.

Debe contener, según el contenido:

```text
Texto
Títulos
Subtítulos
Listas
Enlaces
Imágenes
Tablas
Código
Citas
Diagramas o grafos
Videos
Otros elementos necesarios para el artículo
```

Esta flexibilidad permite que los artículos tengan estructuras diferentes sin exigir una estructura rígida equivalente a la utilizada por proyectos o certificaciones.

Cuando el contenido editorial incorpora cambios de idioma dentro de un artículo, esa información debe conservarse durante su procesamiento y representación.

El frontend no determina el idioma de fragmentos del contenido mediante análisis automático.

Volver al índice [aquí](../README.md#índice).
