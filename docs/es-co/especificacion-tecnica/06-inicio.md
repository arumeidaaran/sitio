# 06. Inicio

Inicio utiliza la estructura general definida para la aplicación y añade una organización específica para el contenido principal y el área de exposición.

No incorpora una segunda región de presentación inmediatamente después de la cabecera.

La identidad principal ya se encuentra representada mediante:

```text
Fondo visual y foto juntos
Nombre
Descripción breve
```

No debe duplicarse esta función mediante una segunda cabecera visual o una sección introductoria equivalente.

No deben añadirse frases de efecto, citas ni elementos editoriales adicionales que no formen parte del contenido definido para Inicio.

---

## Estructura general

Conceptualmente:

```text
Inicio
|
+-- Cabecera
|
+-- Cuerpo
    |
    +-- Navegación
    |
    +-- Contenido principal
    |   |
    |   +-- Proyectos destacados
    |   |
    |   +-- Artículos destacados
    |   |
    |   +-- Certificaciones destacadas
    |
    +-- Área de exposición
        |
        +-- Actualizaciones
```

Las secciones del contenido principal se disponen verticalmente.

Conceptualmente:

```text
Proyectos destacados
        |
        V
Artículos destacados
        |
        V
Certificaciones destacadas
```

Cada sección utiliza el ancho disponible de la columna principal.

No deben organizarse como columnas paralelas que compitan entre sí por el espacio principal.

---

## Secciones destacadas

Las secciones destacadas presentan contenido seleccionado editorialmente.

La composición no depende de una cantidad fija de elementos.

Los componentes deben admitir variaciones en la cantidad recibida sin cambiar la estructura general de Inicio.

Cada sección termina con un acceso explícito hacia su listado completo.

Conceptualmente:

```text
Sección destacada
|
+-- título
|
+-- elementos
|
+-- acceso al listado completo
```

El acceso debe indicar explícitamente su destino.

Las tarjetas de contenido destacado utilizan la misma regla de rejilla adaptable establecida en [Rejilla](./14-tarjetas.md#rejilla).

El acceso al listado completo constituye un objetivo interactivo independiente y aplica el mínimo definido en [Objetivos interactivos](./15-iconos-y-controles.md#objetivos-interactivos).

---

## Proyecto destacado

Cada proyecto destacado presenta:

```text
Imagen
Nombre
Descripción
Ver proyecto
```

La imagen funciona como apoyo visual del proyecto.

El nombre constituye el identificador principal visible.

La descripción debe ser breve y adecuada para una representación resumida.

Los lenguajes y sus porcentajes no se presentan en la tarjeta de Inicio.

La tarjeta completa no constituye implícitamente un enlace.

---

## Artículo destacado

Cada artículo destacado presenta:

```text
Imagen
Título
Descripción
Fecha de publicación
Leer artículo
```

El título constituye el identificador principal visible.

La descripción resume el contenido del artículo.

La fecha se presenta como metadato.

No se requiere una categoría para representar visualmente el artículo.

La tarjeta completa no constituye implícitamente un enlace.

---

## Elemento destacado de Certificaciones

La sección debe representar:

```text
Certificado
Certificación
```

Cada elemento presenta la información resumida necesaria para reconocer el elemento y acceder a su página individual.

La tarjeta completa no constituye implícitamente un enlace.

---

## Coherencia entre destacados

Los diferentes tipos de elemento no necesitan contener exactamente los mismos campos internos.

La coherencia visual debe mantenerse mediante:

```text
Jerarquía tipográfica
Espaciado
Tratamiento de imagen
Metadatos
Posición del enlace
Separación entre elementos
```

La uniformidad visual no debe forzar contratos idénticos entre tipos de contenido diferentes.

Dentro de un mismo tipo de elemento, las tarjetas deben mantener una estructura visual consistente.

El cambio de tema no cambia la estructura interna, el orden, el contenido ni la disposición correspondiente al ancho disponible.

Las tarjetas deben aumentar su altura cuando el texto redimensionado o el espaciado configurado por el usuario requieren más espacio.

No debe limitarse su altura para mantener una alineación visual a costa del contenido.

---

## Área de exposición

El área de exposición solamente existe en Inicio.

Su función es presentar actividad reciente del sitio sin competir visualmente con las secciones principales.

La región utiliza:

```text
Actualizaciones

Novedades y contenido reciente
```

como título y descripción de contexto.

Conceptualmente:

```text
Actualizaciones
|
+-- actualización
|
+-- actualización
|
+-- ...
```

La composición no depende de una cantidad fija de elementos.

Debe admitir variaciones en la cantidad disponible sin cambiar la estructura general del área.

No deben añadirse dentro de esta región citas, frases de efecto ni otros bloques que no representen una actualización.

---

## Actualización

Cada actualización debe representar actividad relacionada con:

```text
Proyecto
Artículo
Certificado
Certificación
```

El acontecimiento debe representar:

```text
Contenido nuevo
Contenido actualizado
```

Cada elemento presenta:

```text
Icono
Tipo de acontecimiento
Nombre o título
Descripción
Fecha
Enlace explícito
```

El icono funciona como apoyo visual para identificar el tipo de contenido o actividad.

El icono debe corresponder al mapeo definido en [Tipos de contenido y acciones](./15-iconos-y-controles.md#tipos-de-contenido-y-acciones).

No debe sustituir el texto necesario para comprender el acontecimiento.

El tipo de acontecimiento debe encontrarse visualmente diferenciado del nombre o título del elemento.

La descripción debe permanecer breve.

La fecha se presenta como metadato.

El enlace debe indicar explícitamente el destino correspondiente.

Conceptualmente:

```text
Proyecto
=> Ver proyecto

Artículo
=> Leer artículo

Certificado
=> Ver certificado

Certificación
=> Ver certificación
```

La tarjeta completa de actualización no constituye implícitamente un enlace.

La acción explícita constituye el objetivo interactivo y aplica el tamaño mínimo definido para controles independientes.

---

## Relación entre contenido principal y exposición

En escritorio amplio:

```text
ancho >= 1360px
```

el contenido principal y el área de exposición utilizan regiones laterales distintas.

```text
Contenido principal
=> selección editorial
=> mayor jerarquía
=> mayor espacio disponible

Área de exposición
=> actividad reciente
=> representación más compacta
=> jerarquía secundaria
```

El área de exposición no debe dominar visualmente la página.

La atención principal permanece en el contenido destacado.

---

## Inicio en escritorio intermedio

Cuando:

```text
1024px <= ancho < 1360px
```

Actualizaciones deja de ocupar la columna lateral de `320px`.

Pasa al flujo de la columna principal después de las secciones destacadas.

El orden es:

```text
Proyectos destacados
Artículos destacados
Certificaciones destacadas
Actualizaciones
```

La naturaleza de Actualizaciones no cambia.

Solamente cambia su posición dentro de la composición.

---

## Inicio en pantallas estrechas

Cuando:

```text
ancho < 1024px
```

Inicio utiliza una composición global vertical.

Conceptualmente:

```text
Cabecera
Navegación móvil
Proyectos destacados
Artículos destacados
Certificaciones destacadas
Actualizaciones
```

El orden editorial de las secciones se conserva.

Actualizaciones no utiliza una columna lateral.

Las rejillas internas siguen presentando tantas tarjetas completas como permita el ancho disponible.

La composición debe continuar funcionando sin pérdida de contenido ni funcionalidad hasta un ancho de `320px CSS`.

---

