# 01. Arquitectura

## Presentación del proyecto

Frontend del sitio personal, desarrollado con Angular y orientado a contenido, internacionalización e integración con sitio-api.

## Objetivo

`Sitio` constituye la capa de frontend del sitio personal.

Su función es presentar la información personal, proyectos, certificaciones, medios de contacto y artículos mediante una interfaz multilingüe, manteniendo separadas la presentación, la navegación, el estado de la aplicación y las fuentes de contenido.

El frontend será publicado mediante GitHub Pages y consumirá los servicios proporcionados por `sitio-api`.

## Organización general

El proyecto forma parte de una arquitectura separada entre frontend y backend.

```text
Usuario
  |
  V
sitio
Angular
GitHub Pages
  |
  | HTTPS
  V
sitio-api
  |
  V
Contenido, servicios y fuentes de datos
```

`Sitio` constituye una aplicación independiente de `sitio-api`.

El frontend es responsable de la presentación, navegación, internacionalización de la interfaz, selección del idioma, selección del tema y estado necesario para la experiencia del usuario.

`Sitio-api` es responsable de obtener, validar, normalizar, seleccionar y exponer el contenido utilizado por el frontend, además de informar los metadatos lingüísticos correspondientes a cada contenido.

Esta separación evita que el frontend dependa directamente de las fuentes originales de datos.

Conceptualmente:

```text
Presentación y navegación
=> sitio

Selección del idioma a mostrar
=> sitio

Selección del tema
=> sitio

Contenido y metadatos
=> sitio-api

Selección y composición de los datos solicitados
=> sitio-api

Fuentes de datos
=> administradas por sitio-api
```

La aplicación es construida como un sitio estático y publicada mediante GitHub Pages.

Node.js participa en el desarrollo, las pruebas y la construcción del proyecto, pero no constituye un servidor de ejecución en producción.

```text
Código fuente
GitHub
      |
      V
Construcción Angular
      |
      V
Archivos estáticos
      |
      V
GitHub Pages
      |
      V
Navegador
```

## Artefactos y sus permisos

Las partes principales relacionadas con el frontend tienen la siguiente disponibilidad:

| Artefactos               | Permiso             |
| ------------------------ | ------------------- |
| Repositorio del proyecto | Público en GitHub   |
| Sitio publicado          | Público en Internet |
| Servicio de sitio-api    | Público en Internet |

El repositorio contiene el código fuente necesario para construir el frontend.

GitHub Pages publica los archivos estáticos generados durante la construcción y los expone mediante HTTPS.

El contenido dinámico utilizado por la aplicación es solicitado a `sitio-api` mediante HTTP.

El frontend no accede directamente a las fuentes internas utilizadas por el backend.

## Estructura funcional

El sitio se organiza mediante un contexto de idioma que contiene todas las páginas visibles.

Conceptualmente:

```text
sitio
|
+-- idioma
    |
    +-- Inicio
    |
    +-- Sobre mí
    |
    +-- Contactos
    |
    +-- Certificaciones
    |   |
    |   +-- Certificado
    |   |
    |   +-- Certificación
    |
    +-- Proyectos
    |   |
    |   +-- Proyecto
    |
    +-- Artículos
        |
        +-- Artículo
```

La página inicial también pertenece al contexto de un idioma.

No existe una versión de contenido independiente de la internacionalización.

La raíz del sitio constituye un punto de entrada encargado de determinar el idioma con el que debe iniciarse la aplicación.

La forma conceptual de las rutas visibles es:

```text
/{idioma}/
=> página inicial localizada

/{idioma}/{seccion-localizada}/
=> sección localizada

/{idioma}/{seccion-localizada}/{slug-localizado}/
=> recurso localizado
```

Los segmentos visibles de la dirección forman parte de la internacionalización de la interfaz.

El `slug` identifica públicamente una versión localizada de un recurso.

Conceptualmente:

```text
Recurso
|
+-- identificador interno
|
+-- versiones localizadas
    |
    +-- idioma
    |   +-- slug
    |
    +-- idioma
        +-- slug
```

El identificador interno representa el mismo recurso independientemente del idioma.

El `slug` pertenece a la variante lingüística y debe ser legible para el público correspondiente a ese idioma.

No es necesario que diferentes idiomas compartan el mismo `slug`.

