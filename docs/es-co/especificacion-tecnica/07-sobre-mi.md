# 07. Sobre mí

Volver al índice [aquí](../README.md#índice-1).

`Sobre mí` combina contenido textual con elementos visuales relacionados directamente con aquello que se está comunicando.

La página no debe convertirse en una sucesión extensa de texto sin pausas visuales.

---

## Estructura

Conceptualmente:

```text
Sobre mí
|
+-- bloque
|   |
|   +-- icono o imagen
|   +-- texto
|
+-- bloque
|   |
|   +-- texto
|   +-- icono o imagen
|
+-- ...
```

La composición debe distribuir texto y elemento visual a uno u otro lado.

La posición forma parte de la composición editorial del frontend.

No debe producirse una alternancia automática solamente por la posición del bloque dentro de la lista. Lo que determina la alternancia de contenido es la regla interna de diseño del frontend.

---

## Relación entre texto y elemento visual

El icono o la imagen debe representar aquello de lo que habla el bloque.

No debe utilizarse como relleno decorativo independiente del contenido.

La elección entre:

```text
Icono
Imagen
```

es una decisión editorial.

No existe una regla general que obligue a utilizar una imagen para determinado tipo de concepto y un icono para otro.

---

## Bloque con icono

Cuando el contenido establece que el elemento visual es un icono:

```text
type = icon
```

`Sitio` selecciona el icono concreto correspondiente mediante el identificador del bloque.

Los identificadores y sus iconos se encuentran definidos en [Sobre mí](./15-iconos-y-controles.md#sobre-mí).

Conceptualmente:

```text
id del bloque
        |
        V
mapeo de Sobre mí
        |
        V
icono concreto de @tabler/icons-angular
```

La API no determina:

```text
Nombre de icono de Tabler
Variante gráfica
Posición
Tamaño
Color
Estilo
```

Cuando un identificador utiliza `type = icon`, debe existir una correspondencia definida en el mapeo técnico.

No se selecciona dinámicamente otro icono por similitud semántica.

---

## Bloque con imagen

Cuando el elemento visual es una imagen:

```text
type = image
```

la imagen dispone de:

```text
src
alt
href
```

Los tres valores existen para este tipo de elemento.

`src` determina qué imagen se representa.

`alt` contiene la alternativa textual determinada por `sitio-api` para la función de la imagen dentro de ese bloque.

`href` determina el destino asociado.

El frontend utiliza directamente el valor de `alt` recibido. No genera una alternativa a partir del título o del texto del bloque, no sustituye el valor recibido y no decide por su cuenta si la alternativa debe quedar vacía.

La imagen de `Sobre mí` representa normalmente información relacionada con el contenido del bloque.

Cuando su función es informativa, `alt` comunica de forma breve la información visual que aporta.

Cuando la imagen constituye por sí misma la representación de una acción o un destino, `alt` comunica la función correspondiente.

Cuando la imagen no debe añadir información diferente a la ya disponible en el contexto, `sitio-api` proporciona:

```text
alt = ""
```

El valor de `alt` no utiliza `null`.

Cuando `href` convierte la imagen en un objetivo interactivo independiente, el enlace aplica el tamaño mínimo general establecido para los objetivos interactivos.

---

## Adaptación responsive

En escritorio debe mantenerse la composición horizontal definida editorialmente entre texto y elemento visual.

Cuando la composición horizontal deja de caber correctamente por el ancho disponible o por el crecimiento del texto, el bloque se reorganiza verticalmente.

El elemento visual utiliza el ancho disponible y mantiene sus proporciones.

El orden editorial de cada bloque se conserva.

No se genera automáticamente una alternancia basada en:

```text
posición impar
posición par
índice del bloque
```

La adaptación cambia la disposición necesaria, no el orden editorial.

---

Volver al índice [aquí](../README.md#índice-1).
