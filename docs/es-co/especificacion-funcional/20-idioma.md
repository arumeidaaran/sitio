# 20. Idioma

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
Idioma principal del documento
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
    +-- idioma semántico del documento y del contenido
```

El backend no decide cuál idioma debe exhibir el frontend.

Las etiquetas utilizadas siguen el formato BCP 47.

El idioma activo del sistema determina también el idioma semántico principal del documento.

Cuando una variante de contenido utiliza el mismo idioma, debe utilizar el contexto lingüístico ya establecido.

Cuando una variante se presenta en otro idioma mediante las reglas de respaldo, solamente el contenido correspondiente adopta semánticamente ese idioma.

La interfaz continúa utilizando el idioma activo.

En una colección, cada unidad debe utilizar el idioma de su propia variante sin obligar a que todas las demás unidades adopten el mismo contexto lingüístico.

Los cambios de idioma que formen parte del propio contenido deben conservarse y declararse en la parte correspondiente.

El frontend no deduce estos cambios mediante análisis automático del texto.

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

Su valor debe cambiarse sin alterar la lógica general de selección del idioma.

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
        |       +-- establecer idioma del documento
        |       +-- cargar elementos
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

Una falla al obtener contenido desde el backend no cambia automáticamente el idioma activo ya determinado por el frontend.

La presentación de la página ocurre después de determinar el idioma activo y preparar los elementos correspondientes, evitando mostrar temporalmente una variante diferente.

El idioma semántico principal del documento debe corresponder al idioma activo ya resuelto antes de presentar la aplicación.

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

Si la escritura en `localStorage` no logra realizarse después de resolver correctamente un idioma válido, el idioma obtenido continúa siendo utilizado durante ese acceso.

La imposibilidad de persistir la preferencia no invalida el idioma ya resuelto.

## Selección de idioma

Es permitido al usuario cambiar explícitamente el idioma mediante los controles proporcionados por la interfaz.

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
Actualizar idioma principal del documento
        |
        V
Cargar página equivalente
```

La aplicación no cambia el idioma de forma automática durante la navegación normal.

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

Cada variante debe disponer de su propio `slug`.

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

Los cambios lingüísticos deliberados dentro de una variante forman parte de su contenido editorial y deben conservarse durante el procesamiento.

No se utiliza detección automática del idioma para reconstruir información lingüística que debe formar parte del contenido.

