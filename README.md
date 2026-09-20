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
    +-- Sobre mí
    |
    +-- Contactos
    |
    +-- Certificaciones
    |   |
    |   +-- Certificación
    |
    +-- Proyectos
    |   |
    |   +-- Proyecto
    |
    +-- Blog
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

## Estructura de las páginas

Las páginas comparten una estructura general común.

```text
Aplicación
|
+-- Cabecera
|   |
|   +-- Fondo visual
|   +-- Foto
|   +-- Nombre
|   +-- Descripción breve
|
+-- Cuerpo
    |
    +-- Navegación
    |   |
    |   +-- Selección de idioma
    |   +-- Selección de tema
    |   +-- Secciones
    |
    +-- Contenido principal
    |
    +-- Área de exposición
        => solamente en Inicio
```

No existe un pie global.

La cabecera constituye una única composición visual formada por el fondo, la fotografía, el nombre y la descripción breve.

Durante el desplazamiento, la cabecera reduce su presencia manteniendo visibles la fotografía y el nombre.

La descripción breve pertenece al estado expandido y no necesita permanecer visible cuando la cabecera se encuentra compactada.

La navegación es vertical y permanece disponible durante el desplazamiento.

Los controles de idioma y tema aparecen directamente al comienzo de la navegación.

No se encuentran ocultos dentro de una sección adicional de configuración.

La navegación organiza primero los accesos directos:

```text
Inicio
Sobre mí
Contactos
```

Después presenta las secciones que contienen recursos y representan parte de su jerarquía:

```text
Certificaciones
Proyectos
Blog
```

Conceptualmente:

```text
Navegación
|
+-- Inicio
+-- Sobre mí
+-- Contactos
|
+-- Certificaciones
|   |
|   +-- Certificación
|   +-- Certificación
|   +-- ...
|   +-- Ver todas las certificaciones
|
+-- Proyectos
|   |
|   +-- Proyecto
|   +-- Proyecto
|   +-- ...
|   +-- Ver todos los proyectos
|
+-- Blog
    |
    +-- Artículo
    +-- Artículo
    +-- ...
    +-- Ver todos los artículos
```

La navegación no reproduce necesariamente todos los elementos existentes.

Cuando una sección puede crecer indefinidamente, presenta una cantidad limitada de elementos y un acceso explícito a la sección completa.

El acceso al listado completo debe indicar el destino correspondiente.

Conceptualmente:

```text
Ver todos los proyectos

Ver todos los artículos

Ver todas las certificaciones
```

Si la navegación supera el espacio vertical disponible, dispone de desplazamiento interno.

La región principal presenta el contenido correspondiente a la página activa.

La navegación interna conserva el contexto lingüístico previamente establecido y utiliza ese mismo idioma para construir el acceso hacia las demás secciones.

## Inicio

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

### Proyectos destacados

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

La cantidad no constituye una limitación estructural del componente.

Al final de la sección se presenta:

```text
Ver todos los proyectos
```

### Artículos destacados

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

### Certificaciones destacadas

La sección presenta certificaciones seleccionadas editorialmente.

Cada elemento presenta:

```text
Imagen o credencial
Nombre
Entidad
Fecha
Enlace explícito
```

La cantidad no constituye una limitación estructural del componente.

Al final de la sección se presenta:

```text
Ver todas las certificaciones
```

### Destacados

La condición de destacado constituye una decisión editorial sobre un recurso.

Conceptualmente:

```text
Recurso
|
+-- destacado
|   |
|   +-- sí
|   |   => puede aparecer en Inicio
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

Los recursos pueden ser seleccionados y ordenados deliberadamente.

### Actualizaciones

El área de exposición de Inicio presenta novedades y contenido reciente.

Conceptualmente:

```text
Actualizaciones

Novedades y contenido reciente

[actualización]
[actualización]
...
```

Esta región puede contener actividad relacionada con:

```text
Proyecto
Artículo
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

El tipo de acción del enlace depende del recurso.

Conceptualmente:

```text
Proyecto
=> Ver proyecto

Artículo
=> Leer artículo

Certificación
=> Ver certificación
```

Las actualizaciones se ordenan de acuerdo con la fecha de actividad, desde la más reciente hacia la menos reciente.

No existe un período temporal fijo para determinar qué contenido puede aparecer.

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

Un mismo recurso puede pertenecer simultáneamente a ambas regiones.

## Contenido

El frontend presenta diferentes tipos de contenido obtenidos mediante `sitio-api`.

La distribución conceptual es:

```text
Sobre mí
=> información personal
=> presentación

Contactos
=> medios de contacto

Certificaciones
=> listado
=> información individual

Proyectos
=> listado
=> información individual

Blog
=> listado de artículos
=> artículos
```

`Sitio` no depende del origen físico de esta información.

Las fuentes utilizadas para generar cada recurso pertenecen a la responsabilidad de `sitio-api`.

Esto permite que la presentación mantenga una estructura estable independientemente de si el backend obtiene determinada información desde archivos locales, Markdown, una base de datos, GitHub u otras fuentes.

La cantidad de información retornada depende del contexto en el que el recurso será utilizado.

Conceptualmente:

```text
Inicio
=> datos necesarios para representar la página inicial

Listado
=> datos necesarios para representar el listado

Detalle
=> contenido completo del recurso
```

El frontend no necesita recibir en Inicio información que solamente será utilizada dentro de la página individual de un recurso.

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
Segmentos visibles de las rutas
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

Los textos que forman parte de la interfaz son administrados por `sitio`.

Los mensajes técnicos retornados por `sitio-api` no se utilizan directamente como textos visibles de la interfaz.

Conceptualmente:

```text
Mensaje técnico de sitio-api
=> diagnóstico y contrato

Texto presentado al usuario
=> recurso localizado de sitio
```

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

Los segmentos visibles de las direcciones y los `slug` correspondientes a recursos forman parte de la variante localizada.

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

## Selección de tema

El usuario puede cambiar explícitamente entre los temas disponibles mediante un control visible al comienzo de la navegación.

El cambio de tema modifica exclusivamente la representación visual de la aplicación sin modificar:

```text
Idioma activo
Dirección
Página activa
Contenido
Selección editorial
Orden de los contenidos
Jerarquía
Navegación
Disposición de las regiones
```

Los diferentes temas constituyen representaciones visuales de la misma estructura y contenido.

Conceptualmente:

```text
Misma página
Mismos contenidos
Mismo orden
Misma jerarquía
Misma disposición
        |
        V
Cambio de tema
        |
        V
Diferente representación visual
```

Cambiar el tema no provoca una nueva selección, reorganización ni sustitución de los contenidos mostrados.

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

Cada variante puede disponer de su propio `slug`.

Conceptualmente:

```text
Contenido
|
+-- variante
|   +-- idioma
|   +-- slug
|
+-- variante
    +-- idioma
    +-- slug
```

El `slug` no será generado mediante traducción automática, sino que será definido editorialmente de forma adecuada para cada idioma.

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

`Sitio-api` compone las respuestas de acuerdo con el contexto solicitado.

Conceptualmente:

```text
Inicio
=> sitio-api selecciona y compone los datos necesarios
=> sitio representa el resultado

Listado
=> sitio-api retorna los datos necesarios para listar
=> sitio representa el resultado

Detalle
=> sitio-api retorna el contenido completo
=> sitio representa el resultado
```

La división de responsabilidades es:

```text
sitio-api
=> retornar contenido
=> exponerlo mediante HTTP
=> informar idioma original de cada contenido
=> informar idiomas soportados por cada contenido
=> retornar content para el idioma solicitado
=> retornar valor nulo en el contenido cuando el idioma del contenido solicitado no existe
=> seleccionar los contenidos destacados
=> ordenar los contenidos destacados
=> seleccionar las actualizaciones
=> ordenar las actualizaciones por fecha de actividad
=> retornar solamente la información necesaria para cada contexto

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
=> construir las rutas visibles localizadas
=> representar la información recibida
=> informar al usuario cuando el contenido se presenta en otro idioma
```

`Sitio-api` no selecciona automáticamente una variante lingüística alternativa cuando el idioma solicitado no existe.

`Sitio` no necesita conocer cómo el backend obtiene o almacena las distintas variantes del contenido.

Ambas capas se comunican únicamente mediante los contratos correspondientes.

### Convenciones internas

La implementación técnica utiliza nombres en inglés para:

```text
Variables
Funciones
Clases
Schemas
Propiedades de modelos
Contratos
Nombres internos de recursos
```

Los textos humanos propios del proyecto deben permanecer en español cuando corresponden a:

```text
Mensajes
Errores técnicos
Documentación
Descripciones
```

Los textos visibles de la interfaz pertenecen a los recursos localizados de `sitio`.

Esta separación evita mezclar el idioma de la implementación con el idioma presentado al usuario.

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

Su estructura interna depende del tipo de recurso y es definida por el contrato específico correspondiente.

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

### Contratos de recursos

El objeto `content` utiliza nombres técnicos en inglés.

El `slug` forma parte del contenido localizado.

### Proyecto

La representación completa de un proyecto contiene conceptualmente:

```json
{
    "slug": "recurso-localizado",
    "name": "...",
    "description": "...",
    "content": "...",
    "image": {
        "src": "...",
        "alt": "..."
    },
    "technologies": [
        "..."
    ],
    "links": [
        {
            "type": "...",
            "url": "..."
        }
    ]
}
```

`description` representa una descripción breve.

`content` representa el contenido completo del proyecto.

`image` contiene la imagen principal y su descripción alternativa.

`technologies` contiene las tecnologías asociadas al proyecto.

`links` contiene los enlaces externos disponibles.

No todos los proyectos necesitan disponer de los mismos tipos de enlace.

### Artículo

La representación completa de un artículo contiene conceptualmente:

```json
{
    "slug": "recurso-localizado",
    "title": "...",
    "description": "...",
    "content": "...",
    "image": {
        "src": "...",
        "alt": "..."
    },
    "publication_date": "...",
    "update_date": null
}
```

`description` representa un resumen breve.

`content` representa el contenido completo del artículo.

`publication_date` identifica la fecha de publicación.

`update_date` identifica una actualización posterior cuando exista.

No se requiere una categoría para representar el artículo.

### Certificación

La representación completa de una certificación contiene conceptualmente:

```json
{
    "slug": "recurso-localizado",
    "name": "...",
    "issuer": "...",
    "description": "...",
    "content": "...",
    "image": {
        "src": "...",
        "alt": "..."
    },
    "issue_date": "...",
    "expiration_date": null,
    "credential": {
        "code": null,
        "url": null
    }
}
```

`issuer` identifica la entidad emisora.

`issue_date` identifica la fecha de emisión.

`expiration_date` puede ser nulo cuando la certificación no dispone de expiración.

`credential` contiene la información de verificación cuando exista.

## Contrato de Inicio

Inicio es solicitado mediante la raíz localizada de la API.

Conceptualmente:

```text
GET /api/v1/{idioma}/
```

`Sitio-api` compone en una sola respuesta los datos necesarios para representar la página inicial.

Conceptualmente:

```json
{
    "status": "ok",
    "status_code": 200,
    "message": "Contenido disponible.",
    "data": {
        "featured_projects": [],
        "featured_articles": [],
        "featured_certifications": [],
        "updates": []
    }
}
```

Cada elemento destacado mantiene los metadatos lingüísticos correspondientes al recurso.

Conceptualmente:

```json
{
    "original": "idioma-a",
    "supported": [
        "idioma-a",
        "idioma-b"
    ],
    "content": {}
}
```

Inicio recibe solamente los datos necesarios para representar sus elementos.

No recibe automáticamente el contenido completo de cada recurso.

### Proyecto destacado

Conceptualmente:

```json
{
    "original": "idioma-a",
    "supported": [
        "idioma-a",
        "idioma-b"
    ],
    "content": {
        "slug": "recurso-localizado",
        "name": "...",
        "description": "...",
        "image": {
            "src": "...",
            "alt": "..."
        }
    }
}
```

La representación de Inicio no necesita recibir:

```text
Contenido completo
Tecnologías
Enlaces externos
```

Estos datos pertenecen al detalle del proyecto.

### Artículo destacado

Conceptualmente:

```json
{
    "original": "idioma-a",
    "supported": [
        "idioma-a",
        "idioma-b"
    ],
    "content": {
        "slug": "recurso-localizado",
        "title": "...",
        "description": "...",
        "image": {
            "src": "...",
            "alt": "..."
        },
        "publication_date": "..."
    }
}
```

### Certificación destacada

Conceptualmente:

```json
{
    "original": "idioma-a",
    "supported": [
        "idioma-a",
        "idioma-b"
    ],
    "content": {
        "slug": "recurso-localizado",
        "name": "...",
        "issuer": "...",
        "image": {
            "src": "...",
            "alt": "..."
        },
        "issue_date": "..."
    }
}
```

### Actualización

Las actualizaciones forman una lista compuesta por proyectos, artículos y certificaciones.

Cada elemento informa el tipo de recurso y el acontecimiento representado.

Conceptualmente:

```json
{
    "type": "tipo-de-recurso",
    "update_type": "tipo-de-actualizacion",
    "activity_date": "...",
    "original": "idioma-a",
    "supported": [
        "idioma-a",
        "idioma-b"
    ],
    "content": {
        "slug": "recurso-localizado",
        "name": "...",
        "description": "..."
    }
}
```

El nombre concreto dentro de `content` puede variar según el tipo de recurso cuando su contrato utiliza una propiedad diferente, como ocurre con el título de un artículo.

`update_type` distingue conceptualmente entre:

```text
Contenido nuevo
Contenido actualizado
```

`activity_date` determina el orden cronológico de la sección.

La inclusión de un contenido entre los destacados y su inclusión entre las actualizaciones constituyen decisiones independientes.

Conceptualmente:

```text
Destacado
=> selección editorial
=> orden editorial

Actualización
=> inclusión independiente
=> tipo de actualización
=> fecha de actividad
```

La selección y orden de los destacados pertenecen a `sitio-api`.

La selección de las actualizaciones también pertenece a `sitio-api`.

Las actualizaciones son ordenadas mediante la fecha de actividad. No se aplica un período fijo para excluir contenido antiguo.

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

Los `slug` deben pertenecer a la variante lingüística correspondiente y ser válidos dentro del contexto en el que identifican el recurso.

La validación debe permitir detectar inconsistencias entre:

```text
Metadatos lingüísticos
Contenido disponible
Idioma original
Idiomas soportados por el contenido
Slug localizado
Recursos de interfaz
Selección de destacados
Orden de destacados
Actualizaciones
Fecha de actividad
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
Slug localizado
Cambio de tema
Conservación del contenido durante el cambio de tema
Conservación del orden y la estructura durante el cambio de tema
Comunicación con sitio-api
Carga de Inicio
Contenido destacado
Actualizaciones
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
