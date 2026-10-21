# 03. Infraestructura

Volver al índice [aquí](../README.md#índice).

## Versionado

El proyecto mantiene dos versiones independientes: la versión del proyecto y la versión de la aplicación publicada.

La versión del proyecto pertenece a los metadatos administrados mediante el sistema de paquetes. Su actualización corresponde al mantenimiento técnico del proyecto y no determina por sí sola que deba publicarse una nueva versión de la aplicación.

La versión de la aplicación se conserva en un recurso estático independiente que forma parte de los archivos generados durante la construcción.

Conceptualmente:

```text
Versión del proyecto
=> metadatos del proyecto
=> mantenimiento de la base técnica

Versión de la aplicación
=> recurso estático propio
=> identificación de la aplicación publicada
=> condición de publicación
```

Ambas versiones pueden evolucionar independientemente.

Los cambios en documentación, herramientas, configuraciones auxiliares o demás archivos que no requieren una nueva publicación no obligan a cambiar la versión de la aplicación.

La decisión de publicar se expresa mediante una modificación del recurso que contiene la versión de la aplicación.

La automatización observa los cambios de ese recurso y no presupone que cualquier modificación del repositorio corresponde a una nueva publicación.

## Despliegue

El frontend se publica mediante `GitHub Actions` en `GitHub Pages`.

El proceso de producción construye la aplicación Angular y publica el resultado estático generado.

La construcción utiliza la ruta base correspondiente al lugar donde se aloja el sitio y conserva separada la configuración de desarrollo de la publicación.

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

La construcción de producción utiliza las dependencias registradas por el proyecto y produce los archivos estáticos necesarios para el funcionamiento de la aplicación.

La publicación utiliza exclusivamente el artefacto construido a partir del código aprobado de la rama principal.

El proceso de construcción y el de publicación constituyen trabajos separados. La publicación solamente puede ejecutarse después de que la construcción termine satisfactoriamente.

La incorporación de cambios a la rama principal no implica automáticamente una nueva publicación.

El workflow de publicación se activa cuando una actualización de la rama principal modifica el recurso utilizado para identificar la versión de la aplicación.

Conceptualmente:

```text
Actualización de main
    |
    +-- cambia la versión de la aplicación
    |       |
    |       V
    |   Construcción de producción
    |       |
    |       V
    |   Publicación en GitHub Pages
    |
    +-- no cambia la versión de la aplicación
            |
            +-- conservar la publicación existente
```

La publicación utiliza el mecanismo de despliegue de `GitHub Pages` mediante `GitHub Actions` y un entorno destinado a esa finalidad.

No se necesita mantener una rama adicional que contenga los archivos construidos para realizar esta publicación.

## Integración y promoción

La rama `dev` constituye la rama de integración del proyecto.

El trabajo se realiza mediante ramas dedicadas y posteriormente es integrado en `dev`.

La rama `main` conserva el código aprobado y dispone de reglas de protección que restringen sus actualizaciones directas.

La promoción automática utiliza una identidad de aplicación autorizada específicamente para actualizar la rama principal.

Las credenciales de esa identidad se administran mediante variables y secretos del repositorio y no forman parte del código fuente.

El token habitual de validación no recibe por sí mismo autorización para modificar la rama protegida.

Las funciones de integración, validación, promoción y publicación se mantienen distribuidas entre workflows independientes.

El flujo habitual es:

```text
Rama de trabajo
    |
    V
   dev
    |
    V
Validación automatizada
    |
    V
Resultado satisfactorio
    |
    V
Promoción mediante identidad autorizada
    |
    V
   main
```

La validación se ejecuta cuando se actualiza `dev` o cuando se solicita integrar una rama de trabajo mediante un pull request hacia ella.

La validación de un pull request es un mecanismo de respaldo y se necesita disactivar la protección de la rama main, por lo que solamente autorizados pueden hacerlo.

Cuando termina la validación, un workflow independiente comprueba el resultado y el origen de la ejecución antes de realizar la promoción.

El commit promovido corresponde al commit que superó las validaciones. No se sustituye automáticamente por un commit posterior que pudiera encontrarse en `dev` sin haber sido validado.

Conceptualmente:

```text
Validación
=> identifica commit comprobado

Resultado satisfactorio
=> habilita promoción

Promoción
=> utiliza commit comprobado
=> actualiza main
```

Existe una segunda vía de promoción mediante pull request dirigido desde `dev` hacia `main`.

Esta vía es independiente del workflow de promoción automática y realiza sus propias validaciones antes de integrar el pull request.

La promoción mediante pull request utiliza la operación correspondiente de GitHub y comprueba que el commit integrado sea el que fue validado.

Conceptualmente:

```text
Pull request de dev hacia main
      |
      V
Validación propia
      |
      V
Resultado satisfactorio
      |
      V
Integración del pull request
      |
      V
main
```

Ambas vías de promoción utilizan la misma identidad autorizada para el frontend y comparten un mecanismo de concurrencia que impide realizar actualizaciones simultáneas de `main`.

Cuando un cambio ya fue incorporado mediante otra promoción, el procedimiento alternativo debe reconocer que no existen cambios pendientes y evitar una integración innecesaria.

La identidad utilizada para promover el frontend es independiente de las identidades utilizadas por otros repositorios.

La promoción hacia `main` debe ocurrir únicamente después de completar correctamente las validaciones definidas para el proyecto.

Las pruebas automatizadas forman parte de esta validación y deben aprobarse en su totalidad.

Las comprobaciones manuales de accesibilidad que resulten aplicables al cambio también deben completarse antes de la promoción, sin constituir una ejecución automatizada adicional que impida por sí misma el flujo de promoción.

La publicación del sitio utiliza el contenido aprobado de la rama principal, pero permanece condicionada al mecanismo de versionado de la aplicación.

Volver al índice [aquí](../README.md#índice).
