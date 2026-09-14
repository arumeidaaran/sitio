# sitio

Frontend del sitio personal, desarrollado con Angular y orientado a contenido, internacionalización e integración con sitio-api.

## Objetivo

`Sitio` constituye la capa de frontend del sitio personal.

Su función es presentar la información personal, proyectos, certificaciones, medios de contacto y publicaciones mediante una interfaz multilingüe, manteniendo separadas la presentación, la navegación, el estado de la aplicación y las fuentes de contenido.

El frontend será publicado mediante GitHub Pages y consumirá los servicios proporcionados por `sitio-api`.

## Arquitectura

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

`Sitio` constituye una aplicación independiente de `sitio-api`. El frontend es responsable de la presentación, navegación, internacionalización de la interfaz y estado necesario para la experiencia del usuario.

`Sitio-api` es responsable de obtener, validar, normalizar y exponer el contenido utilizado por el frontend.

Esta separación evita que el frontend dependa directamente de las fuentes originales de datos.

Conceptualmente:

```text
Presentación y navegación
=> sitio

Contenido y servicios
=> sitio-api

Fuentes de datos
=> administradas por sitio-api
```

La aplicación es construida como un sitio estático y publicada mediante GitHub Pages. Node.js participa en el desarrollo, las pruebas y la construcción del proyecto, pero no constituye un servidor de ejecución en producción.

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

El contenido dinámico utilizado por la aplicación es solicitado a `sitio-api` mediante HTTP. El frontend no accede directamente a las fuentes internas utilizadas por el backend.

## Tecnologías

El frontend utiliza `TypeScript` y `Angular` como base de la aplicación. JavaScript puede formar parte del proyecto cuando corresponda a herramientas o configuraciones que lo utilicen de forma natural, manteniendo TypeScript como lenguaje principal del código de la aplicación.

`Tailwind CSS` proporciona las utilidades utilizadas para construir la presentación visual. El diseño del sitio es propio y no depende de una biblioteca de componentes visuales prediseñados.

La comunicación HTTP con `sitio-api` utiliza `HttpClient` de Angular.

El estado propio de la aplicación utiliza los recursos proporcionados por Angular, principalmente `Signals` y servicios, sin incorporar una biblioteca externa de administración de estado mientras no exista una necesidad concreta.

`Node.js` y `npm` proporcionan el entorno y la gestión de dependencias necesarios durante desarrollo, pruebas y construcción.

Las pruebas utilizan `Vitest` para pruebas unitarias, las herramientas de pruebas de Angular para componentes y servicios, y `Playwright` para pruebas completas ejecutadas mediante navegador.

GitHub Actions será utilizado para los procesos automatizados de validación, integración, construcción y publicación.

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
    +-- Perfil
    |
    +-- Certificaciones
    |   |
    |   +-- Certificación
    |
    +-- Proyectos
    |   |
    |   +-- Proyecto
    |
    +-- Contactos
    |
    +-- Blog
        |
        +-- Artículo
```

La página inicial también pertenece al contexto de un idioma. No existe una versión de contenido independiente de la internacionalización.

La raíz del sitio constituye un punto de entrada encargado de determinar el idioma con el que debe iniciarse la aplicación.

La forma conceptual de las rutas es:

```text
/{idioma}/
=> página inicial localizada

/{idioma}/{seccion}/
=> sección localizada

/{idioma}/{seccion}/{recurso}/
=> recurso localizado
```

Los nombres definitivos utilizados por cada sección en las rutas forman parte de la definición de navegación y no modifican esta jerarquía funcional.

## Estructura de las páginas

Las páginas comparten una estructura general común.

```text
Aplicación
|
+-- Cabecera
|   |
|   +-- Identidad del sitio
|   +-- Navegación
|   +-- Selección de idioma
|
+-- Contenido
|
+-- Pie
```

La cabecera, la navegación y el pie forman parte de la estructura general del sitio. La región principal presenta el contenido correspondiente a la página activa.

La navegación interna conserva el contexto lingüístico previamente establecido y utiliza ese mismo idioma para construir el acceso hacia las demás secciones.

## Contenido

El frontend presenta diferentes tipos de contenido obtenidos mediante `sitio-api`.

La distribución conceptual es:

```text
Perfil
=> información personal
=> presentación
=> datos de contacto

Certificaciones
=> listado
=> información individual

Proyectos
=> listado
=> información individual

Blog
=> listado de publicaciones
=> artículos
```

`Sitio` no depende del origen físico de esta información. Las fuentes utilizadas para generar cada recurso pertenecen a la responsabilidad de `sitio-api`.

Esto permite que la presentación mantenga una estructura estable independientemente de si el backend obtiene determinada información desde archivos locales, Markdown, GitHub u otras fuentes.

## Internacionalización

El sitio utiliza etiquetas de idioma explícitas y mantiene coordinada la internacionalización del frontend con los idiomas admitidos por `sitio-api`.

Los idiomas no son determinados automáticamente mediante la configuración del navegador, la ubicación geográfica ni otras características del dispositivo.

`Sitio-api` constituye la autoridad para determinar qué idiomas son admitidos por el sistema. El frontend mantiene los recursos de interfaz correspondientes a esos mismos idiomas.

Conceptualmente:

```text
Idiomas admitidos por sitio-api
        |
        V
Idiomas disponibles en sitio
```

Un idioma disponible en la aplicación debe poder ser resuelto por ambas capas. Esto evita presentar una interfaz en un idioma que el backend no pueda utilizar para resolver su contenido.

Las etiquetas utilizadas siguen el formato BCP 47.

## Idioma por defecto

El sistema dispone de un idioma por defecto utilizado como respaldo cuando no es posible resolver una alternativa válida.

El valor del idioma por defecto forma parte de la configuración del sistema y no constituye una condición fija de la lógica de navegación.

Todo el frontend debe disponer de una versión completa en el idioma por defecto.

Asimismo, todo contenido publicado debe disponer de una versión en ese idioma.

Conceptualmente:

```text
Contenido publicado
|
+-- idioma por defecto
|   => obligatorio
|
+-- otros idiomas admitidos
    => según disponibilidad
```

Esta condición garantiza que siempre exista una versión utilizable cuando un contenido todavía no esté disponible en otro idioma admitido.

## Resolución del idioma

La resolución del idioma ocurre durante el acceso al sitio.

Cuando la dirección utilizada contiene un idioma, este es validado de acuerdo con los idiomas admitidos por `sitio-api`.

Si el idioma es válido, pasa a constituir el idioma activo y se almacena como preferencia antes de presentar la aplicación.

Conceptualmente:

```text
Acceso con idioma
        |
        V
Validación mediante sitio-api
        |
        +-- idioma válido
        |       |
        |       +-- almacenar preferencia
        |       +-- establecer idioma activo
        |       +-- cargar recursos
        |       +-- presentar
        |
        +-- idioma no admitido
                |
                +-- utilizar idioma por defecto
```

Cuando el acceso ocurre mediante la raíz y no contiene un idioma, la aplicación consulta la preferencia almacenada anteriormente.

```text
Acceso sin idioma
        |
        V
Preferencia almacenada
        |
        +-- válida
        |       |
        |       +-- utilizar preferencia
        |
        +-- ausente o inválida
                |
                +-- utilizar idioma por defecto
```

Si la resolución no puede completarse correctamente, se utiliza el idioma por defecto.

La presentación de la página ocurre después de determinar el idioma activo y preparar los recursos correspondientes, evitando mostrar temporalmente una variante diferente.

## Preferencia de idioma

La preferencia lingüística se conserva localmente mediante `localStorage`.

El almacenamiento sirve para recordar la selección entre diferentes accesos al sitio. No constituye un mecanismo utilizado para volver a determinar el idioma durante cada navegación interna.

La prioridad conceptual es:

```text
Idioma válido de un nuevo acceso
=> utilizar y almacenar

Idioma elegido por el usuario
=> almacenar y utilizar

Preferencia almacenada
=> utilizar en accesos sin idioma definido

Idioma por defecto
=> utilizar como respaldo
```

Una dirección válida tiene prioridad durante el acceso correspondiente.

Si el idioma obtenido mediante la dirección es diferente de la preferencia previamente almacenada, la nueva selección sustituye el valor anterior.

Si la escritura en `localStorage` no puede realizarse después de resolver correctamente un idioma válido, el idioma obtenido continúa siendo utilizado durante ese acceso. La imposibilidad de persistir la preferencia no invalida el idioma ya resuelto.

## Navegación

Después de la resolución inicial, el idioma activo se conserva durante la navegación interna.

El cambio entre páginas no vuelve a consultar ni a modificar la preferencia almacenada.

Conceptualmente:

```text
Acceso
=> resolver idioma

Navegación interna
=> conservar idioma activo

Nuevo acceso
=> resolver nuevamente

Cambio manual de idioma
=> almacenar nueva preferencia
=> establecer nuevo idioma activo
```

Los enlaces internos son construidos de acuerdo con el idioma activo.

Un nuevo acceso directo mediante una dirección diferente vuelve a ejecutar la resolución inicial.

## Selección de idioma

El usuario puede modificar explícitamente el idioma mediante los controles proporcionados por la interfaz.

Una selección válida sustituye la preferencia anterior.

Conceptualmente:

```text
Selección del usuario
        |
        V
Validar idioma
        |
        V
Almacenar preferencia
        |
        V
Establecer idioma activo
        |
        V
Cargar página equivalente
```

La aplicación no modifica el idioma de forma automática durante la navegación normal.

## Disponibilidad de contenido

La disponibilidad global de un idioma y la disponibilidad de un contenido concreto en ese idioma son conceptos distintos.

Un idioma puede estar admitido por el sistema aunque un determinado contenido todavía no disponga de una versión localizada.

Conceptualmente:

```text
Idioma admitido
=> el sistema puede trabajar con ese idioma

Contenido localizado
=> ese recurso concreto dispone de una versión en el idioma
```

Cuando el contenido solicitado existe en el idioma activo, se presenta normalmente.

Cuando el idioma es válido pero el contenido concreto todavía no dispone de esa variante, la aplicación conserva el idioma activo de la interfaz y utiliza la versión del contenido correspondiente al idioma por defecto.

```text
Contenido solicitado
        |
        +-- disponible en idioma activo
        |       |
        |       +-- presentar versión localizada
        |
        +-- no disponible en idioma activo
                |
                +-- conservar idioma de la interfaz
                +-- conservar preferencia
                +-- conservar dirección localizada
                +-- presentar contenido en idioma por defecto
                +-- informar al usuario
```

La ausencia de una traducción no constituye un cambio de preferencia del usuario y no modifica el idioma almacenado.

El aviso correspondiente forma parte de la interfaz y se presenta en el idioma activo.

## Traducciones

Las distintas variantes lingüísticas representan versiones del mismo contenido conceptual.

```text
Contenido
|
+-- idioma por defecto
+-- idioma admitido
+-- idioma admitido
+-- idioma admitido
```

Las traducciones no son tratadas como recursos independientes sin relación entre sí.

No es obligatorio que cada contenido disponga inmediatamente de versiones en todos los idiomas admitidos. La versión correspondiente al idioma por defecto sí es obligatoria para todo contenido publicado.

Las traducciones utilizadas por el sitio representan contenido preparado o revisado para el idioma correspondiente. La generación automática de traducciones no forma parte del mecanismo utilizado para completar variantes ausentes.

## Integración con sitio-api

La comunicación entre el frontend y el backend se realiza mediante HTTPS.

Conceptualmente:

```text
Componente
      |
      V
Servicio
      |
      V
HttpClient
      |
      V
sitio-api
```

Los componentes utilizan los servicios del frontend para acceder a la información necesaria. La comunicación HTTP queda separada de la presentación de las páginas.

El frontend consume los contratos proporcionados por `sitio-api` y no accede directamente a sus fuentes de datos.

La validación de idiomas y la obtención de contenido deben utilizar la información proporcionada por el backend, manteniendo coordinadas ambas capas del sistema.

## Despliegue

El frontend será publicado mediante GitHub Pages.

El proceso de producción construye la aplicación Angular y publica el resultado estático generado.

Conceptualmente:

```text
Código fuente
      |
      V
Construcción
      |
      V
Archivos estáticos
      |
      V
GitHub Pages
      |
      V
Sitio HTTPS
```

GitHub Pages se limita a servir los archivos generados. Angular es ejecutado por el navegador del usuario.

Node.js no permanece en ejecución en producción y el frontend no requiere un servicio de aplicación independiente para su funcionamiento actual.

## Integración y promoción

La rama `dev` constituye la rama de integración del proyecto.

El trabajo se realiza mediante ramas dedicadas y posteriormente es integrado en `dev`.

Conceptualmente:

```text
Rama de trabajo
      |
      V
dev
      |
      V
Validación
      |
      V
main
      |
      V
Construcción
      |
      V
GitHub Pages
```

La promoción hacia `main` debe ocurrir únicamente después de completar correctamente las validaciones definidas para el proyecto.

La publicación del sitio utiliza el contenido aprobado de la rama principal.

## Validación

La aplicación utiliza TypeScript en modo estricto para aumentar la validación estática del código.

Las modificaciones integradas deben verificar el formato, la calidad del código, las pruebas automatizadas y la construcción de producción antes de ser promovidas.

La relación entre los idiomas admitidos por el frontend y los proporcionados por `sitio-api` también forma parte de la consistencia esperada del sistema.

La validación evita publicar una aplicación cuya interfaz no corresponda con los idiomas que el backend declara disponibles.

## Pruebas

Las pruebas automatizadas verifican la lógica del frontend, los servicios, los componentes y la integración entre las partes de la aplicación.

`Vitest` constituye la herramienta principal para pruebas unitarias.

Las herramientas de pruebas de Angular proporcionan el entorno necesario para verificar componentes y servicios relacionados con el framework.

`Playwright` será utilizado para validar mediante navegador los flujos completos que requieran interacción con la aplicación.

Las pruebas deben cubrir especialmente la navegación, resolución del idioma, persistencia de la preferencia, selección manual, comunicación con `sitio-api` y comportamiento cuando un contenido localizado no se encuentra disponible.

## Licencia

Este proyecto está licenciado bajo GNU General Public License v3.0.
