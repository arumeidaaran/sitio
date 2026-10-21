# 19. Pruebas unitarias y navegador

Volver al índice [aquí](../README.md#índice-1).

## Pruebas unitarias

Las pruebas unitarias utilizan Vitest `5`.

La integración se realiza mediante:

```text
@angular/build:unit-test
```

La cobertura utiliza:

```text
@vitest/coverage-v8
```

La configuración de `angular.json` exige:

```json
{
    "coverage": true,
    "coverageThresholds": {
        "statements": 100,
        "branches": 100,
        "functions": 100,
        "lines": 100
    }
}
```

La totalidad de las pruebas unitarias debe aprobarse.

La cobertura medida debe alcanzar el `100%` de instrucciones, ramas, funciones y líneas incluidas en la medición.

El incumplimiento de cualquiera de los umbrales invalida la comprobación correspondiente.

Las herramientas de pruebas de Angular proporcionan el entorno necesario para comprobar componentes, servicios y demás elementos relacionados con el framework.

Los archivos de pruebas unitarias utilizan la extensión:

```text
.spec.ts
```

Las pruebas iniciales verifican la creación de la aplicación y la representación de su título.

Estas pruebas pertenecen a la base generada y deben ampliarse a medida que se implementen los componentes y servicios propios del sitio.

## Pruebas de navegador

Las pruebas de extremo a extremo utilizan Playwright.

La configuración general se encuentra en:

```text
playwright.config.ts
```

La integración con Angular utiliza:

```text
playwright-ng-schematics:playwright
```

La configuración ejecuta pruebas en los siguientes motores:

```text
chromium
firefox
webkit
```

La presencia de Chromium no equivale a ejecutar automáticamente Microsoft Edge, aunque compartan una base tecnológica.

Los archivos de pruebas de extremo a extremo se encuentran en:

```text
e2e/
```

El servidor de desarrollo utilizado por estas pruebas corresponde al proyecto Angular.

La dirección base de desarrollo es:

```text
http://localhost:4200
```

La configuración permite sustituirla mediante:

```text
PLAYWRIGHT_TEST_BASE_URL
```

Durante la integración continua, Playwright utiliza un trabajador para reducir la concurrencia de las pruebas de navegador.

Los intentos adicionales se utilizan solamente según la configuración correspondiente al entorno de integración continua.

La configuración también impide que una prueba marcada para ejecución exclusiva quede inadvertidamente incorporada a la integración continua.

Los informes de pruebas y sus resultados temporales no forman parte del código fuente versionado.

La integración automatizada de las pruebas de accesibilidad utiliza `@axe-core/playwright` conforme a las reglas definidas en la sección de accesibilidad de esta especificación.

La incorporación de las auditorías de accesibilidad a los recorridos concretos debe realizarse junto con la implementación de las páginas, componentes y estados correspondientes.

Volver al índice [aquí](../README.md#índice-1).
