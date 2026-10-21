# 02. Tecnologías

El frontend utiliza `TypeScript` y `Angular` como base de la aplicación.

La aplicación utiliza componentes independientes, enrutamiento propio y detección de cambios sin dependencia de Zone.js.

La aplicación se ejecuta en el navegador y no requiere renderización en servidor.

JavaScript debe formar parte del proyecto cuando corresponda a herramientas o configuraciones que lo utilicen de forma natural, manteniendo TypeScript como lenguaje principal del código de la aplicación.

`Tailwind CSS` proporciona las utilidades utilizadas para construir la presentación visual.

La integración de los estilos utiliza las herramientas de procesamiento correspondientes al proyecto y forma parte de la construcción de Angular.

El diseño del sitio es propio y no depende de una biblioteca de componentes visuales prediseñados.

La iconografía utiliza `@tabler/icons-angular`.

Los iconos forman parte de la presentación administrada por el frontend. Los contratos de `sitio-api` no dependen de los nombres internos ni de la implementación de la biblioteca de iconos.

La comunicación HTTP con `sitio-api` utiliza `HttpClient` de Angular.

El estado propio de la aplicación utiliza los recursos proporcionados por Angular, principalmente `Signals` y servicios, sin incorporar una biblioteca externa de administración de estado mientras no exista una necesidad concreta.

`Node.js` y `npm` proporcionan el entorno y la gestión de dependencias necesarios durante desarrollo, pruebas y construcción.

Las dependencias y los metadatos del proyecto se mantienen mediante el sistema de paquetes correspondiente. El archivo de bloqueo conserva la resolución de dependencias para reproducir las instalaciones.

Las instalaciones automatizadas utilizan las dependencias registradas por el proyecto y respetan las autorizaciones de ejecución de scripts de instalación.

`ESLint`, mediante su integración con Angular, realiza el análisis estático del código y las plantillas. `Prettier` comprueba la aplicación uniforme de las convenciones de formato.

Las convenciones de formato corresponden a las herramientas y lenguajes propios del frontend, sin trasladar reglas particulares de otros ecosistemas. La configuración del editor debe mantener coherencia con el formato establecido.

Las pruebas utilizan `Vitest` para pruebas unitarias, las herramientas de pruebas de Angular para componentes y servicios, y `Playwright` para pruebas completas ejecutadas mediante navegador. Además, `@axe-core/playwright` se integra dentro de las pruebas de accesibilidad.

Las pruebas unitarias utilizan medición de cobertura de instrucciones, ramas, funciones y líneas.

Las pruebas ejecutadas mediante navegador contemplan distintos motores de navegación y sus comportamientos propios.

Las pruebas ejecutadas mediante navegador incorporan una auditoría automática de accesibilidad.

La auditoría automática complementa las comprobaciones manuales de accesibilidad y no las sustituye cuando el aspecto evaluado requiere interpretación humana.

GitHub Actions se utiliza para los procesos automatizados de validación, integración, promoción, construcción y publicación.

