# 18. Ejecutar

Este proyecto utiliza [Angular CLI](https://github.com/angular/angular-cli) versión 22.2.2.


## Servidor de desarrollo

Para iniciar un servidor de desarrollo local, ejecute:

```bash
ng serve
```

Una vez que el servidor esté funcionando, abre tu navegador y navega hasta `http://localhost:4200/`. La aplicación se recargará automáticamente cada vez que modifiques alguno de los archivos fuente.

## Andamiaje de código

Angular CLI incluye potentes herramientas de estructura de código. Para generar un nuevo componente, ejecute:

```bash
ng generate component component-name
```

Para obtener una lista completa de los esquemas disponibles (como `componentes`, `directivas` o `tuberías`), ejecute:

```bash
ng generate --help
```

## Construcción del proyecto

Para crear la ejecución del proyecto:

```bash
ng build
```

Esto compilará tu proyecto y almacenará los artefactos de construcción en el directorio `dist/`. Por defecto, la compilación de producción optimiza tu aplicación para el rendimiento y la velocidad.

## Pruebas unitarias

Para ejecutar pruebas unitarias con el corredor de pruebas [Vitest](https://vitest.dev/), utilice el siguiente comando:

```bash
ng test
```

## Pruebas de extremo a extremo

Para pruebas de extremo a extremo (e2e), ejecute:

```bash
ng e2e
```

Angular CLI no viene con un marco de pruebas de extremo a extremo por defecto. Puede elegir uno que se adapte a sus necesidades.

## Recursos adicionales

Para obtener más información sobre el uso de la CLI angular, incluidas referencias detalladas de comandos, visite la página [Angular CLI Overview and Command Reference](https://angular.dev/tools/cli).
