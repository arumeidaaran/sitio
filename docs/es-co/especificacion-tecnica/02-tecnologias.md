# 02. Tecnologías

Volver al índice [aquí](../README.md#índice-1).

## Base tecnológica de la aplicación

La aplicación frontend utiliza Angular `22.2`, TypeScript `6.0` y Node.js `24`.

El proyecto utiliza `npm` como gestor de paquetes, con la versión `12.2.0` declarada mediante la propiedad `packageManager` de `package.json`.

La aplicación fue creada directamente en la raíz del repositorio existente y conserva su configuración Git y documentación independiente de los archivos generados por Angular.

## Configuración de Angular

La aplicación utiliza componentes independientes mediante `standalone`.

La navegación interna utiliza Angular Router.

La detección de cambios funciona sin Zone.js mediante la configuración `zoneless`.

La aplicación utiliza renderización del lado del cliente y no configura SSR.

La construcción se realiza mediante el ejecutor:

```text
@angular/build:application
```

El servidor de desarrollo utiliza:

```text
@angular/build:dev-server
```

Los archivos principales de configuración son:

```text
angular.json
package.json
package-lock.json
tsconfig.json
tsconfig.app.json
tsconfig.spec.json
```

La configuración de compilación utiliza `src/main.ts` como punto de entrada de la aplicación.

Los recursos estáticos pertenecen a `public/` y son incorporados a la construcción mediante la declaración correspondiente de `assets` en `angular.json`.

Los estilos globales utilizan `src/styles.css`.

El nombre del proyecto Angular es:

```text
sitio
```

La configuración de construcción diferencia entre producción y desarrollo.

La producción utiliza optimización y nombres de recursos con identificadores de contenido mediante:

```json
"outputHashing": "all"
```

Los límites iniciales de construcción son:

```json
{
    "type": "initial",
    "maximumWarning": "500kB",
    "maximumError": "1MB"
}
```

Los límites de estilos de componentes son:

```json
{
    "type": "anyComponentStyle",
    "maximumWarning": "4kB",
    "maximumError": "8kB"
}
```

La configuración de desarrollo mantiene desactivada la optimización de producción y habilita los mapas de código fuente.

La raíz publicada de GitHub Pages utiliza:

```text
/sitio/
```

La construcción destinada a producción establece:

```html
<base href="/sitio/">
```

El artefacto estático de la aplicación se encuentra en:

```text
dist/sitio/browser/
```

`dist/` contiene archivos generados y no forma parte del código fuente versionado.

El servidor de desarrollo de Angular funciona de manera independiente del artefacto generado por la construcción de producción.

## Configuración de TypeScript

TypeScript utiliza el modo estricto de comprobación de tipos.

La configuración general se encuentra en `tsconfig.json`.

`tsconfig.app.json` establece el contexto de compilación de la aplicación y excluye los archivos de pruebas unitarias.

`tsconfig.spec.json` contiene la configuración correspondiente a las pruebas.

La configuración conserva las comprobaciones de Angular para parámetros de inyección y modificadores de acceso.

No se incorporan opciones redundantes cuando su comportamiento ya corresponde a los valores predeterminados de las versiones utilizadas.

El código de la aplicación utiliza TypeScript como lenguaje principal.

JavaScript continúa utilizándose cuando corresponde a archivos de configuración o a herramientas cuya integración natural utiliza ese lenguaje.

## Estilos y procesamiento

La aplicación utiliza Tailwind CSS `4`.

La integración de Tailwind se realiza mediante PostCSS, configurado en `.postcssrc.json`.

Su configuración es:

```json
{
    "plugins": {
        "@tailwindcss/postcss": {}
    }
}
```

Los estilos globales importan Tailwind mediante:

```css
@import "tailwindcss";
```

La identidad visual definida en esta especificación permanece independiente de las utilidades proporcionadas por Tailwind.

La biblioteca de estilos no determina por sí misma los colores, tipografías, proporciones, componentes ni estados visuales propios del sitio.

La aplicación utiliza CSS para las reglas que requieren una definición propia, manteniendo una integración común con la construcción de Angular.

## Análisis estático y formato

El análisis estático utiliza ESLint `10`, TypeScript ESLint y angular-eslint `22`.

La configuración principal se encuentra en:

```text
eslint.config.js
```

El análisis contempla el código TypeScript y las plantillas HTML de Angular.

Las reglas de Angular incorporan comprobaciones para componentes, directivas, plantillas y aspectos automatizables de accesibilidad.

La tarea de análisis está declarada en `angular.json` mediante:

```text
@angular-eslint/builder:lint
```

Los archivos incluidos corresponden a:

```text
src/**/*.ts
src/**/*.html
```

El formato utiliza Prettier `3`.

La configuración se encuentra en `.prettierrc`.

Los valores establecidos son:

```json
{
    "printWidth": 100,
    "singleQuote": false,
    "overrides": [
        {
            "files": "*.html",
            "options": {
                "parser": "angular"
            }
        }
    ]
}
```

Las cadenas de JavaScript y TypeScript utilizan comillas dobles conforme a la convención definida para este proyecto.

Los archivos JSON conservan las reglas sintácticas de JSON.

La configuración de `.editorconfig` mantiene coherencia con las convenciones de formato.

La comprobación automatizada de formato comprende los archivos fuente, las pruebas de navegador y las configuraciones incluidas expresamente en el workflow de validación.

La documentación Markdown mantiene sus propias convenciones editoriales y no queda sometida indiscriminadamente al formato de los archivos de código.

## Dependencias y scripts de instalación

Las dependencias de aplicación y desarrollo se declaran separadamente en `package.json`.

`package-lock.json` conserva la resolución necesaria para reproducir las instalaciones.

La automatización utiliza la instalación reproducible a partir de este archivo de bloqueo.

Los scripts de instalación de dependencias requieren autorización conforme al mecanismo de seguridad de la versión de npm utilizada.

La configuración `allowScripts` contiene las siguientes autorizaciones específicas:

```json
{
    "allowScripts": {
        "@parcel/watcher@2.6.0": true,
        "esbuild@0.28.2": true,
        "lmdb@3.5.6": true,
        "msgpackr-extract@3.0.4": true
    }
}
```

Las autorizaciones están limitadas a los paquetes y versiones declarados.

No se desactiva globalmente el mecanismo de protección de scripts de instalación.

## Estado de la base tecnológica

La base tecnológica queda definida mediante Angular, TypeScript, configuración de construcción y estilos, análisis estático, formato, pruebas unitarias, cobertura, pruebas de navegador, versionado, integración continua, protección de ramas, promoción y publicación.

La aplicación inicial compila con la configuración prevista para GitHub Pages.

Las pruebas iniciales de Vitest alcanzaron los cuatro umbrales de cobertura configurados y las pruebas iniciales de Playwright se completaron correctamente en los tres motores habilitados.

La validación automatizada, la promoción mediante pull request y la publicación en GitHub Pages cuentan con ejecuciones satisfactorias.

El workflow de promoción automática independiente mediante `workflow_run` dispone de la configuración definitiva, aunque su activación deberá confirmarse en una actualización posterior de `dev`.

La implementación de las páginas, componentes, servicios, contratos y comportamiento visual final corresponde a las siguientes etapas del proyecto.

La definición e instalación de la base tecnológica de la etapa 7 queda cerrada.

---

Volver al índice [aquí](../README.md#índice-1).
