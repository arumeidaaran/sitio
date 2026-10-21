# Changelog

Todos los cambios destacados del proyecto y de su capa de publicación se documentan en este archivo.

El formato se basa en [Keep a Changelog](https://keepachangelog.com/es-ES/1.1.0/): entradas cronológicas, fechas ISO 8601 y cambios agrupados por categoría. Las versiones numéricas utilizan [Versionado Semántico](https://semver.org/lang/es/).

El historial distingue dos capas independientes:

- **Proyecto:** documentación, diseño, código, herramientas, pruebas y procesos de desarrollo. Sus entradas identifican las revisiones por fecha; `package.json` administra por separado la versión del paquete.
- **Publicación:** versión de la aplicación indicada en `public/version.json` y mecanismo de construcción y distribución en GitHub Pages. Un cambio de documentación o del proyecto no representa por sí solo una nueva publicación.

Las fechas del historial proceden de los cambios registrados en Git. Las especificaciones describen requisitos; su incorporación a la documentación no implica que la funcionalidad ya esté implementada. Los metadatos de publicación tampoco constituyen por sí solos una prueba de despliegue.

## Proyecto

### 2026-10-21

#### Añadido

- Changelog con el historial del proyecto y de la publicación diferenciados.
- Accesos al changelog y a la licencia desde el README global.
- Documentos de ejecución con propósitos funcionales y técnicos diferenciados.
- Índices de las especificaciones y enlaces de regreso al apartado correspondiente al inicio y al final de sus documentos.

#### Cambiado

- Especificaciones extensas distribuidas en documentos temáticos dentro de las divisiones funcional y técnica de `docs/es-co/`.
- README global convertido en menú de idiomas y documentación española centralizada mediante `docs/es-co/README.md`.
- Archivos ordenados mediante nombres numerados, desde arquitectura y tecnologías hasta componentes y aspectos transversales, con Accesibilidad al final.
- Objetivos de las divisiones aclarados para distinguir el comportamiento esperado de las decisiones de implementación.

#### Corregido

- Jerarquía y títulos de los encabezados internos, eliminando la numeración heredada de los documentos anteriores.
- Referencias a apartados antiguos sustituidas por enlaces a sus ubicaciones actuales.
- Rutas relativas y enlaces de los índices de documentación.

### 2026-10-11

#### Añadido

- Base de Angular con TypeScript, componentes independientes, configuración de enrutamiento y construcción estática; integración de Tailwind CSS.
- Entorno con Node.js y npm, instalación reproducible de dependencias y autorizaciones específicas para sus scripts de instalación.
- Configuración de ESLint, Prettier y herramientas del editor.
- Infraestructura de pruebas unitarias con Vitest y cobertura, y de pruebas de navegador con Playwright para Chromium, Firefox y WebKit.
- Comandos de desarrollo, generación de código, construcción y pruebas.
- Validación automatizada de formato, código, pruebas, cobertura y construcción en GitHub Actions.
- Procesos de promoción de `dev` a `main`, con autenticación mediante una GitHub App y comprobación del código validado.
- Versión inicial del paquete del proyecto `0.0.0` en `package.json`, independiente de la versión de publicación.

#### Cambiado

- Validación de `dev` separada de la promoción automática a `main`.
- Promoción mediante pull request incorporada como flujo adicional con validaciones propias.

#### Corregido

- Convenciones del editor para mantener coherencia con el formato del proyecto.

### 2026-10-09

#### Añadido

- Especificación de interacción mediante ratón, tacto y lápiz: tamaño de objetivos, independencia de hover, activación, cancelación, gestos y ausencia de arrastre obligatorio.
- Estrategia de pruebas de accesibilidad automatizadas y manuales, con cobertura por páginas, estados, temas, idiomas y mecanismos de interacción.
- Requisitos documentados de integración de axe-core, ausencia de violaciones dentro del alcance configurado y comprobaciones humanas complementarias.

#### Corregido

- Terminología y redacción de las especificaciones para mantener coherencia entre requisitos funcionales y técnicos.

### 2026-10-08

#### Añadido

- Requisitos de ampliación de texto y zoom, reflujo, espaciado del texto y funcionamiento en distintas orientaciones.
- Reglas para conservar contenido y controles, y limitar el desplazamiento horizontal a componentes que lo necesitan.

### 2026-10-07

#### Añadido

- Reglas de idioma semántico para el documento, las variantes de contenido, los idiomas de respaldo y los fragmentos multilingües.
- Requisitos de localización de nombres accesibles y alternativas textuales, junto con sus comprobaciones.

### 2026-10-06

#### Añadido

- Clasificación funcional de imágenes y reglas de alternativas textuales para las distintas páginas y recursos.
- Responsabilidad de `sitio-api` sobre el texto alternativo y representación de ese valor por el frontend.

### 2026-10-05

#### Añadido

- Requisitos de gestión del foco, título del documento y anuncio de contexto durante la navegación interna.
- Semántica del envío en curso del formulario de contacto: estado ocupado, campos temporalmente de solo lectura, envío indisponible y conservación del foco.

### 2026-10-04

#### Añadido

- Tokens y auditoría de contraste del tema oscuro.
- Tratamiento de contraste sobre la fotografía de la cabecera y requisitos para foco, bordes, enlaces y estados semánticos.

### 2026-10-03

#### Añadido

- Tokens y auditoría de contraste del tema claro.
- Reglas de accesibilidad para colores, superficies, controles y estados, diferenciando los requisitos de texto y de información visual funcional.

### 2026-09-30

#### Añadido

- Especificación responsive para escritorio amplio, escritorio intermedio y pantallas estrechas.
- Reglas de reorganización de cabecera, navegación, rejillas, formularios y contenido ancho, conservando información y funcionalidad.

### 2026-09-25

#### Añadido

- Estados comunes de carga, contenido vacío, error y contenido no encontrado.
- Estados de cabecera, navegación y formulario de contacto, con tratamiento independiente por región de contenido.

### 2026-09-24

#### Añadido

- Referencias visuales de las páginas y sus listados y detalles en temas claro y oscuro.

#### Cambiado

- Definición de las páginas ampliada con las estructuras y los elementos propios de cada tipo de contenido.
- Modelos visuales organizados por tema y ampliados más allá de la página inicial.

### 2026-09-22

#### Añadido

- Especificaciones de las páginas internas de Sobre mí, Contactos, Certificaciones, Proyectos y Artículos.
- Biblioteca y mapeo de iconos para navegación, controles globales y tipos de contenido.

### 2026-09-20

#### Cambiado

- Reglas de composición del sitio y de los temas ajustadas para mantener coherencia entre las páginas y sus componentes.

### 2026-09-19

#### Añadido

- Especificación inicial de identidad visual: tipografía, paletas, espaciado, dimensiones, cabecera, navegación y tarjetas.
- Modelos visuales de la página inicial para temas claro y oscuro.

#### Cambiado

- Definición de Inicio ampliada con su estructura y distribución del contenido.
- Referencias visuales ajustadas a las decisiones de composición documentadas.

### 2026-09-16

#### Añadido

- Separación de responsabilidades entre el frontend y `sitio-api`.
- Contratos e integración para presentar contenido personal, proyectos, artículos, certificaciones y medios de contacto.

### 2026-09-14

#### Añadido

- Fundación del repositorio y documentación inicial del sitio personal.
- Definición de la organización funcional, navegación y presentación de contenido.
- Licencia GNU General Public License v3.0.

## Publicación

### [0.0.0][0.0.0] - 2026-10-11

#### Añadido

- Construcción y publicación mediante GitHub Actions y GitHub Pages al modificar `public/version.json` en `main`.
- Distribución de los archivos de `dist/sitio/browser/` con la ruta base `/sitio/`.

#### Corregido

- Versión inicial de publicación ajustada de `0.1.0` a `0.0.0`, manteniendo su administración separada de la versión del paquete.

### 0.1.0 - 2026-10-11

#### Añadido

- Primer valor de versión de aplicación en `public/version.json`, creado junto con la base de Angular y la automatización de publicación.

Esta entrada registra un valor histórico de configuración, corregido posteriormente el mismo día. No se presenta como una versión desplegada confirmada.

[0.0.0]: https://github.com/arumeidaaran/sitio/blob/main/public/version.json
