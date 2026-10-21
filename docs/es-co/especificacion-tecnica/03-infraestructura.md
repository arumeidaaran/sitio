# 03. Infraestructura

## Versionado

El frontend mantiene separadas la versión del proyecto y la versión de la aplicación.

La versión del proyecto está definida mediante:

```text
package.json
=> version
```

La versión de la aplicación está definida mediante:

```text
public/version.json
=> version
```

El valor inicial de ambas versiones es:

```text
0.0.0
```

El recurso estático de versión utiliza la estructura:

```json
{
    "version": "0.0.0"
}
```

La versión del proyecto identifica los metadatos del paquete administrado mediante npm.

La versión de la aplicación identifica la publicación del frontend.

La actualización de la versión del proyecto no obliga a publicar automáticamente una versión nueva de la aplicación.

La versión de la aplicación constituye un recurso estático incorporado a la construcción de producción.

La modificación de `public/version.json` dentro de una actualización de `main` determina la activación del workflow de publicación.

El workflow no interpreta necesariamente si el número es mayor que el anterior.

La condición de activación corresponde al cambio del archivo observado por GitHub Actions.

## Ramas y protección

El repositorio mantiene las siguientes responsabilidades:

```text
feature/*
=> desarrollo de cambios concretos

dev
=> integración y validación

main
=> código aprobado
```

Las ramas de trabajo se incorporan a `dev`.

La rama `main` dispone del conjunto de reglas:

```text
Proteger la main
```

Esta protección restringe las actualizaciones directas, la eliminación, la creación de referencias protegidas y las modificaciones no rápidas del historial.

La promoción autorizada utiliza una GitHub App propia del repositorio `sitio`.

La identidad de promoción es independiente de la utilizada por `sitio-api`.

La GitHub App dispone de los permisos necesarios para escribir contenido y actualizar workflows, y figura como excepción autorizada en las reglas de protección de `main`.

Las credenciales utilizadas por la automatización corresponden a:

```text
Variable:
APP_CLIENT_ID

Secreto:
APP_PRIVATE_KEY
```

La clave privada no se almacena en el código fuente del proyecto.

Los tokens de promoción se generan durante la ejecución de los trabajos que los necesitan.

Los trabajos de validación no reciben permisos de escritura sobre `main`.

## Automatización de integración y promoción

GitHub Actions utiliza cuatro workflows independientes dentro de:

```text
.github/workflows/
```

Las responsabilidades se dividen en:

```text
Integración y validación
Promoción automática
Promoción mediante pull request
Construcción y publicación
```

### Integración y validación desde dev

Archivo:

```text
Integración y validación de sitio desde dev.yml
```

El workflow se activa mediante:

```yaml
on:
  pull_request:
    branches:
      - dev
  push:
    branches:
      - dev
```

La validación se ejecuta sobre un entorno de Ubuntu con Node.js `24`.

Los trabajos verifican:

```text
Instalación reproducible de dependencias
Formato del código
Análisis estático
Pruebas unitarias
Cobertura
Instalación de navegadores de prueba
Pruebas de extremo a extremo
Construcción de producción
```

La validación debe terminar satisfactoriamente para que una actualización de `dev` pueda ser utilizada por la promoción automática.

Este workflow no contiene un trabajo que actualice directamente `main`.

### Promoción automática desde dev hacia main

Archivo:

```text
Promoción de sitio desde dev hacia main.yml
```

El workflow utiliza el acontecimiento `workflow_run`:

```yaml
on:
  workflow_run:
    workflows:
      - Integración y validación de sitio desde dev
    types:
      - completed
    branches:
      - dev
```

La promoción comprueba:

```text
Resultado de la validación
=> success

Acontecimiento que originó la validación
=> push

Rama validada
=> dev

Repositorio de origen
=> sitio
```

Solamente una ejecución que satisfaga estas condiciones permite la promoción.

El commit promovido se obtiene mediante:

```text
github.event.workflow_run.head_sha
```

La promoción no sustituye ese identificador por la referencia actual de la rama.

La GitHub App obtiene un token temporal y realiza la integración mediante la API de GitHub:

```http
POST /repos/{owner}/{repo}/merges
```

El cuerpo conceptual utilizado es:

```json
{
    "base": "main",
    "head": "sha-del-commit-validado",
    "commit_message": "Integrar cambios validados de dev en main"
}
```

La operación respeta las reglas de protección de la rama principal mediante la identidad autorizada.

### Promoción mediante pull request

Archivo:

```text
Promoción de sitio mediante pull request.yml
```

Este workflow constituye una vía alternativa independiente de la promoción automática.

La activación corresponde a pull requests dirigidos a `main`:

```yaml
on:
  pull_request:
    branches:
      - main
    types:
      - opened
      - reopened
      - ready_for_review
      - synchronize
```

La validación solamente se ejecuta cuando:

```text
Rama de origen
=> dev

Rama de destino
=> main

Repositorio de origen
=> mismo repositorio

Pull request en borrador
=> false
```

El workflow ejecuta nuevamente la instalación reproducible, el formato, el análisis estático, las pruebas unitarias, la cobertura, las pruebas de navegador y la construcción de producción.

La aprobación de esas verificaciones habilita el trabajo de promoción.

La promoción comprueba previamente si el commit pendiente ya está incorporado a `main`.

La comparación utiliza:

```http
GET /repos/{owner}/{repo}/compare/main...{sha}
```

Cuando no existen commits pendientes, la integración adicional se omite.

Cuando existen cambios pendientes, la GitHub App integra el pull request mediante:

```http
PUT /repos/{owner}/{repo}/pulls/{pull_number}/merge
```

El cuerpo incluye:

```json
{
    "merge_method": "merge",
    "sha": "sha-del-commit-validado",
    "commit_title": "Integrar pull request de dev hacia main"
}
```

La propiedad `sha` evita integrar un commit diferente del que fue validado.

El pull request se integra mediante la operación específica de GitHub y no mediante la integración directa de ramas utilizada por el workflow automático.

### Concurrencia de las promociones

Ambas vías de promoción comparten:

```yaml
concurrency:
  group: sitio-promocion-main
  cancel-in-progress: false
  queue: max
```

La configuración evita ejecuciones simultáneas de los trabajos que actualizan `main`.

Las solicitudes pendientes se conservan conforme al comportamiento de concurrencia definido por GitHub Actions.

La concurrencia no vincula las condiciones de activación de ambos workflows.

### Construcción y publicación en GitHub Pages

Archivo:

```text
Construcción y publicación de sitio en GitHub Pages.yml
```

Su activación es:

```yaml
on:
  push:
    branches:
      - main
    paths:
      - "public/version.json"
```

El workflow está dividido en dos trabajos:

```text
construccion
=> construir aplicación
=> preparar artefacto estático

publicacion
=> recibir artefacto construido
=> desplegar en GitHub Pages
```

El segundo trabajo depende de la finalización satisfactoria del primero.

La construcción utiliza Node.js `24` y las dependencias registradas en el archivo de bloqueo.

La compilación de producción utiliza la ruta base `/sitio/`.

Los archivos publicados se obtienen de:

```text
dist/sitio/browser/
```

Las acciones utilizadas son:

```text
actions/checkout@v6
actions/setup-node@v6
actions/configure-pages@v5
actions/upload-pages-artifact@v4
actions/deploy-pages@v4
```

El trabajo de publicación utiliza el entorno:

```text
github-pages
```

Los permisos de ese trabajo corresponden a:

```yaml
permissions:
  pages: write
  id-token: write
```

La publicación no necesita actualizar directamente el código fuente del repositorio.

Los archivos generados son entregados a GitHub Pages mediante un artefacto de Actions.

La actualización de `main` sin cambios en `public/version.json` no activa este workflow.

## Nombres de los workflows

Cada workflow declara un nombre propio mediante `name` y un título de ejecución mediante `run-name`.

Los nombres de los trabajos describen la acción que ejecutan.

Los mensajes de commits creados por las operaciones de promoción pertenecen al historial Git y no determinan el nombre de los workflows.

La identificación visible de los procesos de validación, promoción y publicación debe permitir distinguir sus responsabilidades.

