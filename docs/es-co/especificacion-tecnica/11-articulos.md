# 11. Artículos

La página de Artículos utiliza la rejilla general de tarjetas.

---

## Tarjeta

Cada tarjeta presenta:

```text
------------------------------------
| imagen                           |
| -------------------------------- |
| Título                           |
| Descripción breve                |
| Fecha de publicación             |
| Fecha de actualización           |
| Leer artículo                    |
------------------------------------
```

Todas las tarjetas contienen las dos líneas de fechas, la fecha de publicación y la fecha de actualización.

---

## Fecha de publicación y actualización

La fecha de publicación corresponde a la publicación inicial.

La fecha de actualización corresponde a la última versión publicada.

Cuando todavía no existe un cambio posterior:

```text
Fecha de publicación
=> fecha original

Fecha de actualización
=> misma fecha que la de publicación
```

Cuando existe una actualización posterior:

```text
Fecha de publicación
=> fecha original

Fecha de actualización
=> nueva fecha actualizada
```

No se utiliza una representación visual de:

```text
null
Sin actualizar
```

para este caso.

---

## Artículo

Al seleccionar `Leer artículo`, la región `Contenido` completa representa el artículo.

El cuerpo de los artículos utiliza contenido procedente de Markdown.

El artículo no está obligado a mantener una estructura rígida equivalente a Proyecto o Certificaciones.

debe contener:

```text
Párrafos
Títulos
Subtítulos
Listas
Enlaces
Imágenes
Tablas
Bloques de código
Citas
Diagramas
Grafos
Videos
Otros elementos propios del contenido
```

Los cambios de idioma definidos editorialmente dentro del contenido forman parte de la estructura semántica del artículo.

El procesamiento de Markdown debe conservar la información necesaria para que esos cambios continúen identificados en la representación resultante.

El frontend no analiza automáticamente el texto para inferir el idioma de un fragmento.

Los enlaces integrados dentro del contenido textual siguen siendo enlaces de texto y utilizan las excepciones normativas correspondientes a objetivos incluidos dentro de un bloque textual.

---

## Lectura

La representación del Markdown debe respetar la identidad tipográfica y cromática del sitio.

El contenido proporcionado por Markdown no debe introducir un segundo sistema visual independiente.

Elementos como:

```text
encabezados
enlaces
tablas
código
citas
imágenes
```

deben recibir estilos compatibles con los tokens generales definidos en esta especificación.

En escritorio se conserva el ancho de lectura definido para el contenido principal.

Los textos del artículo utilizan la misma escala tipográfica relativa de la aplicación.

---

## Adaptación responsive del artículo

Cuando:

```text
ancho < 1024px
```

el artículo utiliza el ancho disponible dentro del contenedor y respeta:

```text
padding horizontal => 16px
```

La jerarquía y el orden del contenido Markdown no cambian.

Permanecen en su orden editorial:

```text
Títulos
Párrafos
Listas
Citas
Imágenes
Tablas
Código
Diagramas
Grafos
Videos
```

Las imágenes y demás elementos visuales se redimensionan proporcionalmente cuando siguen siendo legibles.

Para contenidos anchos se utiliza la prioridad:

```text
1. Reorganizar
2. Redimensionar proporcionalmente
3. Adaptar internamente
4. Desplazamiento horizontal propio solamente cuando la estructura bidimensional sea necesaria
```

La página completa no adquiere desplazamiento horizontal por la presencia de una tabla, bloque de código, diagrama u otro elemento.

Una tabla debe adaptarse cuando la reorganización conserva correctamente su información.

Un bloque de código debe ajustarse cuando la división de líneas no altera su significado.

Cuando la relación espacial, la indentación o la estructura bidimensional resultan necesarias para conservar el significado, el componente utiliza desplazamiento horizontal propio.

El desplazamiento utiliza el comportamiento normal disponible para el navegador y no introduce una función personalizada de arrastre obligatoria.

---

