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

`Sitio` constituye una aplicación independiente de `sitio-api`.

El frontend es responsable de la presentación, navegación, internacionalización de la interfaz, selección del idioma y estado necesario para la experiencia del usuario.

`Sitio-api` es responsable de obtener, validar, normalizar y exponer el contenido utilizado por el frontend, además de informar los metadatos lingüísticos correspondientes a cada contenido.

Esta separación evita que el frontend dependa directamente de las fuentes originales de datos.

Conceptualmente:

```text
Presentación y navegación
=> sitio

Selección del idioma a mostrar
=> sitio

Contenido y metadatos
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

## Tecnologías

El frontend utiliza `TypeScript` y `Angular` como base de la aplicación.

JavaScript puede formar parte del proyecto cuando corresponda a herramientas o configuraciones que lo utilicen de forma natural, manteniendo TypeScript como lenguaje principal del código de la aplicación.

`Tailwind CSS` proporciona las utilidades utilizadas para construir la presentación visual.

El diseño del sitio es propio y no depende de una biblioteca de componentes visuales prediseñados.

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

La página inicial también pertenece al contexto de un idioma.

No existe una versión de contenido independiente de la internacionalización.

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

La cabecera, la navegación y el pie forman parte de la estructura general del sitio.

La región principal presenta el contenido correspondiente a la página activa.

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

`Sitio` no depende del origen físico de esta información.

Las fuentes utilizadas para generar cada recurso pertenecen a la responsabilidad de `sitio-api`.

Esto permite que la presentación mantenga una estructura estable independientemente de si el backend obtiene determinada información desde archivos locales, Markdown, GitHub u otras fuentes.

## Internacionalización

El sitio utiliza etiquetas de idioma explícitas.

Los idiomas no son determinados automáticamente mediante la configuración del navegador, la ubicación geográfica ni otras características del dispositivo.

La internacionalización se divide en dos niveles:

```text
Idioma del sistema
=> administrado por sitio

Idioma del contenido
=> seleccionado por sitio
   a partir de los metadatos proporcionados por sitio-api
```

El idioma del sistema controla:

```text
Interfaz
Navegación
Preferencia del usuario
Dirección localizada
```

`Sitio` conoce directamente los idiomas para los que dispone de una interfaz completa y utiliza esta información para validar las direcciones, preferencias y selecciones realizadas por el usuario.

El idioma del contenido determina cuál variante de un recurso debe ser presentada.

Ambos idiomas pueden ser diferentes.

Para cada contenido, `sitio-api` informa:

```text
Idioma original
Idiomas soportados por el contenido
Contenido correspondiente al idioma solicitado
```

`Sitio` utiliza esta información para aplicar sus propias reglas de presentación.

Conceptualmente:

```text
sitio-api
    |
    +-- idioma original del contenido
    +-- idiomas soportados por el contenido
    +-- contenido solicitado
    |
    V
sitio
    |
    +-- idiomas de interfaz
    +-- idioma por defecto
    +-- idioma activo
    +-- preferencia
    +-- reglas de presentación
```

El backend no decide cuál idioma debe exhibir el frontend.

Las etiquetas utilizadas siguen el formato BCP 47.

## Idioma por defecto

El frontend dispone de un idioma por defecto utilizado como respaldo cuando no es posible utilizar el idioma activo.

El idioma por defecto pertenece a la configuración de `sitio`.

`Sitio-api` no necesita conocerlo para aplicar reglas de presentación.

Su valor puede modificarse sin alterar la lógica general de selección del idioma.

Todo el frontend debe disponer de una versión completa en el idioma por defecto.

Asimismo, según las reglas de publicación del sitio, todo contenido debe disponer normalmente de una versión en ese mismo idioma.

Conceptualmente:

```text
Contenido publicado
|
+-- idioma por defecto
|   => obligatorio según las reglas de publicación
|
+-- otros idiomas
    => según disponibilidad
```

La aplicación no presupone que esta regla nunca pueda ser incumplida debido a un error de configuración, contenido o mantenimiento.

Por ese motivo, cuando ni el idioma activo ni el idioma por defecto están disponibles para un contenido, se utiliza el idioma original del recurso.

La prioridad para seleccionar el idioma del contenido es:

```text
1. Idioma activo, patrón o elegido por el usuario
2. Idioma por defecto
3. Idioma original del contenido
```

El idioma original debe existir necesariamente entre los idiomas soportados por el contenido.

## Resolución del idioma

La resolución del idioma del sistema ocurre durante el acceso al sitio.

Cuando la dirección utilizada contiene un idioma, este es validado de acuerdo con los idiomas soportados por la interfaz de `sitio`.

Si el idioma es válido, pasa a constituir el idioma activo y se almacena como preferencia antes de presentar la aplicación.

Conceptualmente:

```text
Acceso con idioma
        |
        V
Validación mediante sitio
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

La resolución del idioma del sistema no depende de la disponibilidad de `sitio-api`.

Una falla al obtener contenido desde el backend no modifica automáticamente el idioma activo ya determinado por el frontend.

La presentación de la página ocurre después de determinar el idioma activo y preparar los recursos correspondientes, evitando mostrar temporalmente una variante diferente.

## Preferencia de idioma

La preferencia lingüística se conserva localmente mediante `localStorage`.

El almacenamiento sirve para recordar la selección entre diferentes accesos al sitio.

No constituye un mecanismo utilizado para volver a determinar el idioma durante cada navegación interna.

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

Si la escritura en `localStorage` no puede realizarse después de resolver correctamente un idioma válido, el idioma obtenido continúa siendo utilizado durante ese acceso.

La imposibilidad de persistir la preferencia no invalida el idioma ya resuelto.

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
Validar mediante idiomas de sitio
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

No existe una variante neutral del contenido sin contexto lingüístico.

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
Presenta la variante seleccionada del contenido
Informa al usuario sobre la diferencia de idioma
```

La ausencia de una traducción no constituye un cambio de preferencia del usuario y no modifica el idioma almacenado.

El aviso correspondiente forma parte de la interfaz y se presenta en el idioma activo del sistema.

## Traducciones

Las distintas variantes lingüísticas representan versiones del mismo contenido conceptual.

```text
Contenido
|
+-- idioma original
+-- idioma soportado
+-- idioma soportado
+-- idioma soportado
```

Las traducciones no son tratadas como recursos independientes sin relación entre sí.

Cada contenido identifica cuál es su idioma original.

Este idioma debe encontrarse siempre entre sus idiomas soportados.

No es obligatorio que cada contenido disponga inmediatamente de versiones en todos los idiomas utilizados por la interfaz.

La versión correspondiente al idioma por defecto del frontend debe existir para todo contenido publicado según las reglas de mantenimiento del sitio.

Si esta condición no se cumple, la aplicación utiliza el idioma original como último respaldo.

Las traducciones utilizadas por el sitio representan contenido preparado o revisado para el idioma correspondiente.

La generación automática de traducciones no forma parte del mecanismo utilizado para completar variantes ausentes.

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

Los componentes utilizan los servicios del frontend para acceder a la información necesaria.

La comunicación HTTP queda separada de la presentación de las páginas.

El frontend consume los contratos proporcionados por `sitio-api` y no accede directamente a sus fuentes de datos.

La división de responsabilidades es:

```text
sitio-api
=> retornar contenido
=> exponerlo mediante HTTP
=> informar idioma original de cada contenido
=> informar idiomas soportados por cada contenido
=> retornar content para el idioma solicitado
=> retornar valor nulo en el contenido cuando el idioma del contenido solicitado no existe

sitio
=> conocer sus idiomas de interfaz
=> mantener el idioma por defecto
=> mantener el idioma activo
=> administrar la preferencia del usuario
=> validar el idioma del sistema
=> seleccionar el idioma de la interfaz
=> seleccionar el idioma del contenido
=> aplicar los respaldos
=> realizar una nueva solicitud cuando sea necesario
=> informar al usuario cuando el contenido se presenta en otro idioma
```

`Sitio-api` no selecciona automáticamente una variante alternativa cuando el idioma solicitado no existe.

`Sitio` no necesita conocer cómo el backend obtiene o almacena las distintas variantes del contenido.

Ambas capas se comunican únicamente mediante el contrato de cada contenido.

### Contrato de contenido

Todo contenido localizado es solicitado directamente mediante una ruta que contiene el idioma deseado.

Conceptualmente:

```text
/api/v1/{idioma}/{recurso}/
```

La solicitud retorna en una sola respuesta:

```text
original
supported
content
```

Conceptualmente, el contrato tiene una única estructura:

```json
{
    "status": "ok",
    "status_code": 200,
    "message": "Contenido disponible.",
    "data": {
        "original": "idioma-a",
        "supported": [
            "idioma-a",
            "idioma-b",
            "idioma-c"
        ],
        "content": {}
    }
}
```

`original` identifica el idioma en el que fue creado el recurso.

`supported` identifica todas las variantes lingüísticas existentes de ese mismo contenido.

`content` representa la variante correspondiente al idioma incluido en la solicitud.

Su estructura interna depende del tipo de recurso y será definida por el contrato específico correspondiente.

Cuando existe la variante solicitada:

```text
content
=> objeto
```

Cuando no existe la variante solicitada:

```text
content
=> null
```

La estructura general del contrato no cambia.

Conceptualmente, una variante ausente mantiene:

```json
{
    "status": "not_found",
    "status_code": 404,
    "message": "Contenido no disponible en el idioma solicitado.",
    "data": {
        "original": "idioma-a",
        "supported": [
            "idioma-a",
            "idioma-c"
        ],
        "content": null
    }
}
```

La diferencia no constituye un segundo contrato.

Es el mismo contrato de contenido con un valor diferente de `content` y un estado HTTP correspondiente a la ausencia de la variante solicitada.

`Sitio-api` no sustituye automáticamente la variante ausente por otra.

La respuesta informa únicamente:

```text
original
=> idioma original

supported
=> variantes disponibles

content
=> contenido solicitado o null
```

A partir de esta información, `sitio` decide qué hacer.

Conceptualmente:

```text
Solicitud:
GET /api/v1/{idioma-activo}/{recurso}/

        |
        V

original
supported
content

        |
        +-- content != null
        |       |
        |       +-- presentar
        |
        +-- content = null
                |
                V
        ¿default está en supported?
                |
                +-- sí
                |     |
                |     +-- solicitar default
                |
                +-- no
                      |
                      +-- solicitar original
```

El valor de `original` debe formar parte necesariamente de `supported`.

El contrato no necesita propiedades adicionales para informar:

```text
idioma solicitado
idioma resuelto
respaldo utilizado
idioma seleccionado finalmente
```

Estas informaciones son conocidas o determinadas por el propio frontend durante la ejecución de sus reglas.

Conceptualmente:

```text
sitio
|
+-- idiomas de interfaz
+-- idioma activo
+-- idioma por defecto
+-- reglas de presentación
|
| idioma deseado
V
sitio-api
|
+-- original
+-- supported
+-- content
```

La forma concreta del objeto contenido en `content` será incorporada conforme los respectivos recursos sean definidos e implementados.

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

GitHub Pages se limita a servir los archivos generados.

Angular es ejecutado por el navegador del usuario.

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

Los idiomas utilizados por la interfaz forman parte de la configuración y los recursos propios de `sitio`.

Los contratos de contenido proporcionados por `sitio-api` deben garantizar:

```text
original pertenece a supported
```

La publicación del contenido debe procurar además:

```text
idioma por defecto pertenece a supported
```

Esta segunda condición constituye una regla de publicación y mantenimiento, pero la aplicación permanece preparada para continuar funcionando si se incumple.

La validación debe permitir detectar inconsistencias entre:

```text
Metadatos lingüísticos
Contenido disponible
Idioma original
Idiomas soportados por el contenido
Recursos de interfaz
```

## Pruebas

Las pruebas automatizadas verifican la lógica del frontend, los servicios, los componentes y la integración entre las partes de la aplicación.

`Vitest` constituye la herramienta principal para pruebas unitarias.

Las herramientas de pruebas de Angular proporcionan el entorno necesario para verificar componentes y servicios relacionados con el framework.

`Playwright` será utilizado para validar mediante navegador los flujos completos que requieran interacción con la aplicación.

Las pruebas deben cubrir especialmente:

```text
Resolución del idioma
Validación mediante los idiomas de interfaz
Persistencia de la preferencia
Selección manual
Navegación localizada
Comunicación con sitio-api
Selección del idioma del contenido
Variante disponible
content = null
Respaldo mediante idioma por defecto
Respaldo mediante idioma original
Conservación del idioma activo del sistema
Aviso cuando el contenido utiliza otro idioma
```

También debe verificarse que una variante ausente conserve `original` y `supported`, permitiendo que el frontend determine correctamente la siguiente solicitud.

## Licencia

Este proyecto está licenciado bajo GNU General Public License v3.0.
