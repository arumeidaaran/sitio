# 19. Adaptación responsive

Volver al índice [aquí](../README.md#índice).

La presentación se adapta al espacio disponible sin reducir la interfaz de escritorio de forma proporcional ni eliminar contenido para hacerla caber.

La adaptación conserva:

```text
Contenido
Jerarquía
Identidad visual
Funciones
Estados
Orden editorial
```

y cambia cuando sea necesario:

```text
Composición
Posición
Ancho disponible
Organización interna
Distribución de tarjetas
```

## Composición general

La aplicación contempla composiciones de escritorio amplio, escritorio intermedio y pantallas estrechas.

En el escritorio amplio, Inicio debe mantener simultáneamente:

```text
Navegación
Contenido principal
Área de exposición
```

Las páginas internas utilizan:

```text
Navegación
Contenido
```

Cuando el espacio de escritorio deja de ser suficiente para mantener correctamente las tres regiones de Inicio, la navegación lateral continúa disponible y el área de exposición pasa a formar parte del flujo principal debajo del contenido destacado.

Las páginas internas continúan utilizando la composición lateral mientras exista espacio suficiente para mantenerla correctamente.

Cuando el espacio disponible requiere abandonar la estructura de escritorio, la aplicación utiliza una composición estrecha formada conceptualmente por:

```text
Cabecera
Navegación
Contenido
```

No se intenta conservar una barra lateral reducida ni comprimir progresivamente todos los elementos para mantener la misma estructura.

## Tipografía y espaciado

La tipografía utiliza una escala correspondiente a las composiciones de escritorio y otra adaptada a las pantallas estrechas.

Los tamaños de texto que no necesitan reducirse mantienen su proporción entre composiciones.

No se introduce una escala intermedia adicional cuando la estructura debe resolverse mediante las escalas establecidas.

La escala tipográfica se implementa de forma relativa al tamaño base configurado por el usuario.

La presentación normal conserva las proporciones tipográficas definidas para el sitio sin impedir que una preferencia distinta del usuario modifique el tamaño efectivo del texto.

Todos los textos visibles de la aplicación forman parte de esta misma capacidad de redimensionamiento.

Esto incluye:

```text
Encabezados
Párrafos
Navegación
Controles
Campos de formulario
Acciones
Metadatos
Etiquetas
Textos auxiliares
Textos presentados dentro de controles
```

Los textos auxiliares presentes dentro de los campos utilizan el mismo tamaño correspondiente al texto del propio control.

Los controles forman parte de la misma escala tipográfica de la interfaz y responden al redimensionamiento del texto.

El espaciado horizontal general se adapta al espacio disponible.

El espaciado interno de los componentes y la separación vertical entre bloques mantienen la escala visual definida cuando no existe una necesidad concreta de reducirlos.

Una pantalla estrecha no implica reducir automáticamente todos los espacios verticales.

Todo contenedor que incluye texto debe crecer cuando el redimensionamiento del texto o el espaciado configurado por el usuario requieren más espacio.

Una dimensión visual definida para la presentación normal no debe recortar, truncar, ocultar ni superponer el contenido.

Conceptualmente:

```text
Dimensión normal
=> referencia de presentación

Texto necesita más espacio
=> contenedor crece
=> contenido permanece completo
```

Los controles y regiones con contenido textual deben aumentar su dimensión necesaria antes de eliminar, recortar o superponer ese contenido.

Los elementos cuya geometría no depende de contenido textual mantienen su dimensión cuando el redimensionamiento del texto no cambia la información ni la funcionalidad que contienen.

## Zoom y reflujo

Las capacidades normales del navegador para ampliar la página y el texto no deben restringirse.

La ampliación debe conservar:

```text
Contenido
Funcionalidad
Navegación
Controles
Estados
Orden
Jerarquía
```

La interfaz utiliza las mismas reglas responsive cuando la ampliación reduce el espacio disponible para la representación.

Conceptualmente:

```text
Menor espacio disponible por tamaño de pantalla
=> aplicar adaptación responsive

Menor espacio disponible por ampliación
=> aplicar adaptación responsive
```

La página debe continuar reorganizándose hasta el ancho mínimo exigido por el nivel de accesibilidad establecido para el proyecto.

Durante este reflujo no debe perderse contenido ni funcionalidad.

La página completa no debe requerir desplazamiento horizontal para acceder al contenido normal.

Las cadenas textuales extensas deben ajustarse dentro del espacio disponible cuando su división no cambia su significado.

Conceptualmente:

```text
Texto normal
=> envolver

Cadena extensa divisible
=> adaptar dentro del contenedor

Contenido cuya estructura horizontal es necesaria
=> tratamiento específico del componente
```

## Contenido ancho

Un componente interno no debe provocar desplazamiento horizontal de la página completa.

Cuando un contenido supera el espacio disponible, se aplica la siguiente prioridad conceptual:

```text
Reorganizar
Redimensionar proporcionalmente
Adaptar internamente
Utilizar desplazamiento horizontal propio solamente cuando la estructura bidimensional deba conservarse
```

La reorganización se utiliza cuando la disposición debe cambiar sin alterar la información ni su significado.

El redimensionamiento se utiliza cuando el elemento debe reducirse manteniendo la legibilidad.

La adaptación interna permite que un componente utilice una representación más adecuada al espacio disponible.

El desplazamiento horizontal se reserva exclusivamente para contenidos cuya estructura bidimensional sea necesaria para su uso, comprensión o significado.

Cuando corresponde este tratamiento, el desplazamiento afecta exclusivamente al componente y no a toda la página.

Un tipo de componente no queda exceptuado automáticamente por su categoría.

Debe utilizar desplazamiento horizontal propio solamente cuando reorganizar, redimensionar o adaptar internamente perjudica la información que necesita conservar.

## Orientación

La aplicación no exige una orientación concreta del dispositivo.

Todo el contenido y toda la funcionalidad deben permanecer disponibles tanto en una orientación vertical como horizontal.

El cambio de orientación aplica las reglas responsive correspondientes al nuevo espacio disponible.

La composición se determina mediante el espacio disponible y no mediante el nombre de la orientación.

La aplicación no debe:

```text
Bloquear una orientación
Exigir girar el dispositivo
Ocultar contenido por la orientación
Ocultar funciones por la orientación
Mantener una función disponible solamente en una orientación
```

## Imágenes y recursos visuales

Las imágenes y demás recursos visuales respetan el espacio disponible de su contenedor.

Se redimensionan proporcionalmente cuando sea necesario.

Un recurso visual que forma parte del contenido o de la identidad de una sección no desaparece automáticamente por utilizar una pantalla estrecha.

La adaptación reorganiza o redimensiona el recurso antes de eliminarlo.

## Botones

Los botones conservan su identidad visual y sus dimensiones entre composiciones.

En las composiciones de escritorio deben utilizar un ancho determinado por su contenido.

En las pantallas estrechas, las acciones principales deben utilizar todo el ancho disponible cuando ello favorece la composición.

El cambio de ancho no cambia el texto ni el estado representado por el control.

Cuando el redimensionamiento del texto exige más espacio, el control debe crecer o reorganizarse antes de recortar, truncar u ocultar su texto.

El área interactiva pertenece al control completo y no solamente al texto o al icono que contiene.

Los controles independientes mantienen un tamaño suficiente para su utilización mediante puntero y tacto.

## Formulario de contacto

Los campos del formulario ya utilizan una disposición vertical y aprovechan el ancho disponible de su región.

Por este motivo, la adaptación responsive no necesita cambiar su orden.

La acción principal utiliza un ancho adecuado a su contenido en las composiciones de escritorio y ocupa el ancho disponible en las pantallas estrechas.

El mismo comportamiento se conserva mientras el envío se encuentra en curso.

Los estados del formulario no cambian por la composición utilizada.

Los campos, etiquetas, instrucciones, errores y controles deben conservarse completos cuando aumenta el tamaño o el espaciado del texto.

## Sobre mí

Los bloques de `Sobre mí` deben utilizar composiciones horizontales entre texto y recurso visual cuando existe espacio suficiente.

En pantallas estrechas, los bloques que ya no caben correctamente se reorganizan verticalmente.

El recurso visual utiliza el ancho disponible y mantiene sus proporciones.

El orden editorial de cada bloque se conserva.

La aplicación no altera automáticamente el orden de texto e imagen en función de la posición del bloque dentro de la página.

## Detalle de proyecto

El detalle de un proyecto debe mantener una composición horizontal entre sus elementos principales mientras exista espacio suficiente.

En una composición estrecha, la imagen y la información relacionada se organizan verticalmente.

La imagen mantiene sus proporciones y utiliza el espacio disponible.

Los grupos de información también deben reorganizarse internamente cuando una disposición horizontal deja de ser adecuada.

El contenido y su orden semántico permanecen iguales.

## Detalle de certificado y certificación

El detalle de un certificado o una certificación debe utilizar una composición horizontal cuando existe espacio suficiente.

En pantallas estrechas, la imagen, la información principal y los datos de la credencial se reorganizan verticalmente.

Cada región utiliza el ancho disponible.

La imagen mantiene sus proporciones.

Los valores representados por el recurso no cambian debido a la composición utilizada.

Un certificado aplica la misma lógica de adaptación utilizando solamente los datos que pertenecen a su propio contrato.

## Artículo

El artículo mantiene su estructura editorial independientemente de la composición utilizada.

En pantallas amplias conserva un ancho de lectura adecuado.

En pantallas estrechas utiliza el ancho disponible del contenedor.

Los elementos que forman parte del Markdown mantienen su jerarquía y su orden, pero se reorganizan adecuándose al espacio disponible.

Conceptualmente:

```text
Títulos
Párrafos
Listas
Citas
Imágenes
Tablas
Código
Diagramas
Gráficos
Videos
```

Las imágenes y otros recursos visuales se redimensionan proporcionalmente cuando sea posible.

Las tablas, bloques de código, diagramas y demás contenidos anchos utilizan las mismas reglas generales de reorganización, redimensionamiento, adaptación interna y desplazamiento propio.

El desplazamiento horizontal propio solamente debe utilizarse cuando la estructura horizontal o bidimensional del contenido necesita conservarse para mantener su significado.

La adaptación responsive no cambia el contenido editorial del artículo.

Volver al índice [aquí](../README.md#índice).
