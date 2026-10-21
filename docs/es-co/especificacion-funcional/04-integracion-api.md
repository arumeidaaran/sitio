# 04. Integración con la API

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
=> sitio-api retorna los datos completos necesarios para representar el elemento
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
=> obtener y normalizar datos de fuentes externas
=> determinar las alternativas textuales de las imágenes de contenido según su función y contexto
=> conservar los cambios lingüísticos definidos editorialmente durante el procesamiento del contenido
=> recibir y procesar el formulario de contacto
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
=> declarar semánticamente el idioma activo del documento
=> declarar el idioma real del contenido cuando difiere del idioma del sistema
=> conservar los cambios lingüísticos internos presentes en el contenido
=> representar la información recibida
=> representar las alternativas textuales recibidas sin generarlas ni sustituirlas
=> seleccionar componentes visuales
=> seleccionar los iconos concretos
=> representar los tipos técnicos mediante textos localizados
=> informar al usuario cuando el contenido se presenta en otro idioma
```

`Sitio-api` no selecciona automáticamente una variante lingüística alternativa cuando el idioma solicitado no existe.

`Sitio-api` tampoco determina la posición, color, tamaño, icono concreto ni demás características propias de la presentación.

La determinación de la alternativa textual de una imagen de contenido forma parte de los datos suministrados y no constituye una decisión visual del frontend.

La declaración semántica del idioma no requiere que `sitio-api` decida el idioma principal de la interfaz.

El frontend ya conoce el idioma activo y el idioma de la variante que finalmente presenta mediante las solicitudes realizadas.

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
Nombres internos de elementos
Valores discriminadores
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

`original` identifica el idioma en el que fue creado el elemento.

`supported` identifica todas las variantes lingüísticas existentes de ese mismo contenido.

`content` representa la variante correspondiente al idioma incluido en la solicitud.

Su estructura interna depende del tipo de elemento y es definida por el contrato específico correspondiente.

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

La declaración semántica del idioma de la variante presentada tampoco requiere una propiedad adicional en el contrato.

El frontend conoce el idioma de la solicitud que produjo el contenido finalmente utilizado.

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

## Contratos de recursos

El objeto `content` utiliza nombres técnicos en inglés.

El `slug` forma parte del contenido localizado cuando el recurso dispone de página individual localizada.

Toda imagen que forme parte de un recurso de contenido contiene obligatoriamente:

```text
src
alt
```

`src` identifica la fuente de la imagen.

`alt` contiene la alternativa textual determinada por `sitio-api` para la función de esa imagen dentro de la representación solicitada.

Las dos propiedades siempre forman parte del contrato cuando existe una imagen de contenido.

`alt` debe contener una alternativa textual a las tecnologías de asistencia, aunque su valor sea de "tipo texto vacío" cuando la imagen no aporta información adicional.

`alt` no utiliza `null`.

El texto de `alt` es localizado.

El frontend utiliza el valor recibido sin generarlo, sustituirlo ni cambiarlo de acuerdo con la posición en la que la imagen se representa.

La misma fuente visual puede disponer de una alternativa distinta en representaciones diferentes cuando su función cambia entre esos contextos.

### Sobre mí

La representación de `Sobre mí` contiene bloques editoriales.

Conceptualmente:

```json
{
    "name": "...",
    "description": "...",
    "blocks": [
        {
            "id": "software",
            "title": "...",
            "text": "...",
            "visual": {
                "type": "icon"
            }
        },
        {
            "id": "music",
            "title": "...",
            "text": "...",
            "visual": {
                "type": "image",
                "src": "...",
                "alt": "...",
                "href": "..."
            }
        }
    ]
}
```

`visual.type` constituye un discriminador.

Los valores utilizados son:

```text
icon
image
```

Cuando `type` es `icon`, el contrato no contiene información específica de una biblioteca gráfica.

El identificador del bloque permite al frontend seleccionar el icono concreto que corresponde editorialmente a ese contenido.

Conceptualmente:

```text
id del bloque
=> mapeo interno de sitio
=> icono concreto de @tabler/icons-angular
```

Cuando `type` es `image`, se incluyen obligatoriamente:

```text
src
alt
href
```

`src` identifica la fuente de la imagen.

`alt` proporciona su alternativa textual.

`href` proporciona el destino asociado a la imagen.

Estos valores no utilizan `null`.

Las decisiones de posición y estilo no forman parte del contrato de `sitio-api`.

### Contactos

Los contactos disponen de un recurso independiente del perfil.

Conceptualmente:

```http
GET /api/v1/{idioma}/contacts/
POST /api/v1/{idioma}/contacts/
```

`GET` obtiene los medios disponibles.

El contrato base contiene conceptualmente:

```json
{
    "linkedin": "...",
    "github": "...",
    "website": null,
    "emails": [
        {
            "type": "tipo",
            "address": "..."
        }
    ],
    "phones": [
        {
            "type": "mobile",
            "format": "nacionalidad",
            "number": "...",
            "whatsapp": true
        }
    ]
}
```

`type` debe contener uno de los valores personal, comercial o empresarial.

`website` debe ser nulo cuando no existe un sitio web adicional disponible.

`whatsapp` indica expresamente si el número telefónico también se utiliza mediante WhatsApp.

Los iconos correspondientes a los medios de contacto son seleccionados por el frontend.

Las tarjetas de Contactos utilizan estos iconos como representación visual del medio y no reciben una imagen de contenido para esta función.

`POST` recibe conceptualmente:

```json
{
    "first_name": "...",
    "last_name": "...",
    "email": "...",
    "subject": "...",
    "message": "..."
}
```

La operación procesa el mensaje mediante `sitio-api` y el servicio configurado para el envío de correo.

Los contactos dejan de formar parte del recurso `profile`.

### Proyecto

La representación completa de un proyecto contiene conceptualmente:

```json
{
    "slug": "recurso-localizado",
    "name": "...",
    "description": "...",
    "image": {
        "src": "...",
        "alt": "..."
    },
    "languages": [
        {
            "name": "lenguaje1",
            "percentage": 85.5
        },
        {
            "name": "lenguaje2",
            "percentage": 14.5
        }
    ],
    "repository_url": "https://github.com/..."
}
```

`description` representa una descripción breve localizada.

`image` contiene la imagen principal y su descripción alternativa.

`languages` contiene los lenguajes detectados para el proyecto y el porcentaje correspondiente a cada uno.

El campo `name` de `languages` debe contener el nombre de un lenguaje de programación.

Los porcentajes son calculados por `sitio-api` a partir de los datos obtenidos mediante GitHub.

`repository_url` identifica el repositorio correspondiente.

El frontend no accede directamente a GitHub.

No se utiliza Markdown para representar el detalle de un proyecto.

La representación resumida utilizada en las tarjetas no necesita recibir los lenguajes ni sus porcentajes.

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
    "update_date": "..."
}
```

`description` representa un resumen breve.

`content` representa el contenido procesado a partir de la fuente Markdown.

`publication_date` identifica la fecha original de publicación.

`update_date` identifica la fecha correspondiente a la última versión publicada.

Ambas propiedades contienen siempre una fecha.

En la primera publicación:

```text
publication_date = update_date
```

Posteriormente:

```text
update_date >= publication_date
```

No se requiere una categoría para representar el artículo.

Los cambios de idioma definidos editorialmente dentro del cuerpo forman parte del contenido procesado y deben conservar su significado lingüístico durante la representación.

### Certificado

Un certificado utiliza el discriminador:

```text
type = certificate
```

Conceptualmente:

```json
{
    "type": "certificate",
    "slug": "recurso-localizado",
    "name": "...",
    "issuer": "...",
    "issue_date": "...",
    "image": {
        "src": "...",
        "alt": "..."
    }
}
```

`issuer` identifica la entidad emisora.

`issue_date` identifica la fecha de emisión o finalización correspondiente.

El contrato de certificado no contiene propiedades propias de una certificación profesional que no le correspondan.

### Certificación

Una certificación utiliza el discriminador:

```text
type = certification
```

Conceptualmente:

```json
{
    "type": "certification",
    "slug": "recurso-localizado",
    "name": "...",
    "issuer": "...",
    "issue_date": "...",
    "expiration_date": null,
    "image": {
        "src": "...",
        "alt": "..."
    },
    "credential": {
        "code": null,
        "url": null
    }
}
```

`issuer` identifica la entidad emisora.

`issue_date` identifica la fecha de emisión.

`expiration_date` contiene la fecha de expiración cuando existe.

Cuando vale `null`, significa que la certificación no expira.

El frontend representa este caso mediante un texto localizado equivalente a:

```text
No expira
```

`credential.code` y `credential.url` siempre forman parte del contrato de certificación.

Cuando alguno no está disponible, su valor es `null`.

El frontend representa esta ausencia mediante un texto localizado equivalente a:

```text
No disponible
```

El frontend no utiliza la presencia o ausencia de propiedades para determinar si un elemento es un certificado o una certificación.

La identificación depende exclusivamente de `type`.

Conceptualmente:

```text
type = certificate
=> contrato Certificate

type = certification
=> contrato Certification
```

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

No recibe automáticamente el contenido completo de cada elemento.

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
Lenguajes
Porcentajes
URL del repositorio
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

La fecha de actualización forma parte del listado completo y del detalle del artículo, pero no es necesaria para la representación resumida establecida para Inicio.

### Elemento destacado de Certificaciones

Conceptualmente:

```json
{
    "original": "idioma-a",
    "supported": [
        "idioma-a",
        "idioma-b"
    ],
    "content": {
        "type": "certificate",
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

o:

```json
{
    "original": "idioma-a",
    "supported": [
        "idioma-a",
        "idioma-b"
    ],
    "content": {
        "type": "certification",
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

`type` permite al frontend determinar qué elemento representa y construir la acción correspondiente.

### Actualización

Las actualizaciones forman una lista compuesta por proyectos, artículos, certificados y certificaciones.

Cada elemento informa el tipo de elemento y el acontecimiento representado.

Conceptualmente:

```json
{
    "type": "tipo-de-elemento",
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

El nombre concreto dentro de `content` debe variar según el tipo de recurso cuando su contrato utiliza una propiedad diferente, como ocurre con el título de un artículo.

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

