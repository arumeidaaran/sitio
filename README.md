# Sitio

La documentación del proyecto está disponible en los siguientes idiomas:

- [Español](docs/es-co/README.md)
- [English](docs/en-us/README.md)
- [Português](docs/pt-br/README.md)
- [日本語](docs/ja-jp/README.md)

La ruta `camino_de_la_documentacion` corresponde a la siguiente estructura de directorios y archivos:

```text
./
|----|docs/
|    |----<idioma>/
|    |    |----especificacion-funcional/
|    |    |    |----01-archivo1.md
|    |    |    |----02-archivo2.md
|    |    |    |----03-archivo3.md
|    |    |    |----04-archivo4.md
|    |    |----especificacion-tecnica/
|    |    |    |----01-archivo1.md
|    |    |    |----02-archivo2.md
|    |    |    |----03-archivo3.md
|    |    |    |----04-archivo4.md
|    |    |----archivo.md
|----README.md
```

Los elementos de esta estructura se definen de la siguiente manera:

**`<idioma>`:** Directorio identificado mediante una etiqueta de idioma conforme al estándar BCP 47, utilizando los siguientes valores:

Español: es-co
English: en-us
Português: pt-br
日本語: ja-jp

**`<número>-archivo.md`:** Archivo cuyo nombre se determina a partir del título principal de la sección correspondiente de la especificación. Se omite la numeración del título si ese existe y se sustituyen los espacios por guiones. También se quita los tildes. `<número>` representa el número del archivo en el orden de los archivos en la carpeta.

Por ejemplo, para el siguiente encabezado:

```markdown
# Especificación técnica de identidad visual

## Estado
```

El nombre del archivo correspondiente será:

> \<numero-del-orden\>-especificación-técnica-de-identidad-visual.md

Para el siguiente encabezado:

```markdown
# 1. Tipografía

## 1.1. Títulos
```

El nombre del archivo correspondiente será:

> \<numero-del-orden\>-tipografía.md

Este criterio de denominación se aplica a los demás archivos de las especificaciones.

**`archivo.md`:** Archivo que centraliza los vínculos de acceso a todas las secciones de la documentación correspondientes a un idioma determinado.

**`README.md`:** Archivo global que centraliza las versiones de documentación por idioma. Es el archivo actual.

Esta estructura establece una organización uniforme para todas las versiones localizadas de la documentación, manteniendo independientes sus respectivos contenidos y facilitando su mantenimiento y actualización.

Para consultar la documentación del proyecto, acceda a la versión correspondiente mediante los vínculos de idioma disponibles al inicio de este documento.

## Historial de cambios

Consulte el [Changelog](./CHANGELOG.md) para conocer los cambios destacados del proyecto.

## Licencia

Este proyecto está licenciado bajo [GNU General Public License v3.0](./LICENSE).
