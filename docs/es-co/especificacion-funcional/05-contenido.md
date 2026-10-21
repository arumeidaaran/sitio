# 05. Contenido

Volver al índice [aquí](../README.md#índice).

El frontend presenta diferentes tipos de contenido obtenidos mediante `sitio-api`.

La distribución conceptual es:

```text
Sobre mí
=> bloques de contenido personal
=> iconos o imágenes relacionados

Contactos
=> medios de contacto
=> formulario

Certificaciones
=> listado de certificados y certificaciones
=> información individual

Proyectos
=> listado
=> información individual

Artículos
=> listado de artículos
=> artículos
=> contenido Markdown
```

`Sitio` no depende del origen físico de esta información.

Las fuentes utilizadas para generar cada elemento pertenecen a la responsabilidad de `sitio-api`.

Esto permite que la presentación mantenga una estructura estable independientemente de si el backend obtiene determinada información desde texto Markdown, una API externa, una base de datos u otras fuentes fuera del propio archivo ubicado por el backend.

La cantidad de información retornada depende del contexto en el que el elemento será utilizado.

Conceptualmente:

```text
Inicio
=> datos necesarios para representar la página inicial

Listado
=> datos necesarios para representar el listado

Detalle
=> datos completos necesarios para representar el elemento
```

El frontend no necesita recibir en Inicio información que solamente será utilizada dentro de la página individual de un recurso.

Markdown se utiliza como fuente editorial de los artículos.

Constituye la fuente general para todos los contenidos de artículos.

## Disponibilidad de contenido

La disponibilidad de un idioma en la interfaz y la disponibilidad de un contenido concreto en ese mismo idioma son conceptos distintos.

`Sitio` conoce los idiomas soportados por su propia interfaz.

Cada contenido retornado por `sitio-api` informa:

```text
original
=> idioma en el que fue creado

supported
=> idiomas en los que ese contenido dispone de una versión

content
=> contenido correspondiente al idioma solicitado
```

Todo contenido localizado es solicitado mediante una ruta que contiene explícitamente el idioma deseado.

Conceptualmente:

```text
/api/v1/{idioma}/{recurso}/
```

La página inicial constituye el contenido raíz localizado de `sitio-api`.

Conceptualmente:

```text
/api/v1/{idioma}/
=> contenido necesario para Inicio
```

La raíz técnica de la API y la página inicial localizada cumplen funciones diferentes.

La resolución del idioma continúa perteneciendo al frontend.

No existe una variante neutral del contenido, visible o no visible, sin contexto lingüístico.

Cada solicitud de contenido retorna conjuntamente:

```text
original
supported
content
```

No existe una solicitud previa separada para obtener únicamente los metadatos lingüísticos del contenido.

Cuando la variante correspondiente al idioma solicitado existe:

```text
content
=> objeto con el contenido solicitado
```

Cuando la variante correspondiente al idioma solicitado no existe:

```text
content
=> null
```

En ambos casos, `original` y `supported` continúan presentes.

El frontend utiliza esta misma respuesta para determinar si debe realizar una nueva solicitud en otro idioma.

Conceptualmente:

```text
Solicitar contenido en idioma activo
        |
        V
sitio-api
        |
        +-- content contiene objeto
        |       |
        |       +-- presentar contenido
        |
        +-- content = null
                |
                V
        consultar supported
                |
                +-- idioma por defecto soportado
                |       |
                |       +-- solicitar idioma por defecto
                |
                +-- idioma por defecto no soportado
                        |
                        +-- solicitar idioma original
```

Cuando el contenido dispone de una versión en el idioma activo, esta es utilizada directamente.

Cuando el idioma activo no está disponible, el frontend intenta utilizar el idioma por defecto.

Si tampoco existe una versión en el idioma por defecto, utiliza el idioma original del contenido.

```text
Idioma activo
      |
      V
¿Está en supported?
      |
      +-- sí
      |     |
      |     +-- usar idioma activo
      |
      +-- no
            |
            V
      Idioma por defecto
            |
            V
      ¿Está en supported?
            |
            +-- sí
            |     |
            |     +-- solicitar idioma por defecto
            |
            +-- no
                  |
                  +-- solicitar original
```

El idioma original constituye una garantía del contenido y debe formar parte de `supported`.

El frontend no selecciona arbitrariamente otra variante existente cuando faltan el idioma activo y el idioma por defecto.

En ese caso utiliza específicamente `original`.

Cuando el idioma utilizado para el contenido difiere del idioma activo del sistema, la aplicación:

```text
Conserva el idioma de la interfaz
Conserva la preferencia
Conserva la dirección localizada
Conserva el idioma principal del documento
Presenta la variante seleccionada del contenido
Declara el idioma real de esa variante
Informa al usuario sobre la diferencia de idioma
```

La ausencia de una traducción no constituye un cambio de preferencia del usuario y no cambia el idioma almacenado.

El aviso correspondiente forma parte de la interfaz y se presenta en el idioma activo del sistema.

La declaración del idioma diferente se aplica al contenido que pertenece a la variante utilizada como respaldo y no a los textos de interfaz que aparecen junto a él.

Cuando una página contiene múltiples recursos, cada recurso puede utilizar una variante lingüística diferente de forma independiente.

La declaración semántica corresponde a cada unidad de contenido y no obliga a cambiar el idioma de toda la colección.

Volver al índice [aquí](../README.md#índice).
