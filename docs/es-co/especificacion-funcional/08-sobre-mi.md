# 08. Sobre mí

`Sobre mí` presenta el contenido personal mediante bloques de texto acompañados por elementos visuales relacionados con aquello que se está comunicando.

Conceptualmente:

```text
Sobre mí
|
+-- bloque
|   +-- texto
|   +-- icono o imagen
|
+-- bloque
|   +-- texto
|   +-- icono o imagen
|
+-- ...
```

Los elementos visuales no se incorporan de forma arbitraria.

Cada icono o imagen debe corresponder al contenido del bloque al que acompaña.

La decisión editorial determina si un bloque utiliza:

```text
Icono
Imagen
```

El contrato permite al frontend conocer cuál de los dos tipos fue seleccionado.

La posición, tamaño, color y demás decisiones de presentación pertenecen exclusivamente a `sitio`.

Cuando el elemento es un icono, `sitio-api` no especifica un icono propio de una biblioteca.

El bloque dispone de un identificador estable y `sitio` relaciona ese identificador con un icono concreto de la biblioteca utilizada por el frontend.

Conceptualmente:

```text
Identificador del bloque
=> sitio

sitio
=> icono concreto de Tabler Icons
```

De esta manera, la elección del icono específico continúa perteneciendo a la capa de presentación.

Cuando el elemento es una imagen, su contrato contiene la fuente de la imagen, el texto alternativo y el destino asociado.

El texto alternativo es definido como parte del contenido y corresponde a la función de la imagen dentro del bloque.

`Sitio` representa el texto alternativo proporcionado por `sitio-api` sin generar, sustituir ni reinterpretar su contenido.

