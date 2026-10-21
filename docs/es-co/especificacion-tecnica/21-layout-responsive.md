# 21. Layout responsive

Volver al índice [aquí](../README.md#índice-1).

## Proporciones del layout

La estructura utiliza tres rangos principales:

```text
ancho >= 1360px
=> escritorio amplio

1024px <= ancho < 1360px
=> escritorio intermedio

ancho < 1024px
=> composición estrecha
```

---

### Escritorio

Mientras la composición de escritorio permanece activa:

#### Navegación

```text
224px
```

Ancho fijo.

No se reduce progresivamente dentro del escritorio.

El contenido textual de la navegación debe envolverse y aumentar verticalmente los elementos correspondientes cuando su tamaño efectivo ya no cabe en una sola línea.

#### Columna principal

```text
mínimo => 720px
óptimo => 1fr
```

#### Área de exposición de Inicio

```text
320px
```

Ancho fijo cuando se utiliza como columna lateral.

#### Ancho máximo del contenido interior principal

```text
960px
```

#### Ancho máximo total previsto

```text
1504px
```

---

### Inicio en escritorio amplio

Cuando:

```text
ancho >= 1360px
```

Inicio utiliza tres regiones horizontales:

```text
| navegación | contenido principal | área de exposición |
|   224px    |        1fr          |       320px        |
```

El contenido principal reúne las secciones de contenido destacado.

El área de exposición reúne la actividad reciente.

El umbral corresponde a la suma mínima necesaria para mantener las regiones y espacios principales:

```text
24px
+ 224px
+ 24px
+ 720px
+ 24px
+ 320px
+ 24px
= 1360px
```

---

### Inicio en escritorio intermedio

Cuando:

```text
1024px <= ancho < 1360px
```

la navegación lateral sigue utilizando:

```text
224px
```

El contenido principal utiliza el espacio restante.

El área de exposición deja de utilizar una columna lateral de `320px`.

Actualizaciones pasa debajo del contenido destacado dentro de la región principal.

Conceptualmente:

```text
| navegación | contenido principal |
|   224px    |        1fr          |

Contenido principal
|
+-- Proyectos destacados
+-- Artículos destacados
+-- Certificaciones destacadas
+-- Actualizaciones
```

No se reduce la navegación, la cabecera ni la fotografía para conservar artificialmente un valor fijo de columnas del escritorio amplio.

---

### Páginas internas en escritorio

Cuando:

```text
ancho >= 1024px
```

las páginas internas no utilizan el área de exposición.

```text
| navegación  | contenido |
|   224px     |    1fr    |
```

La región `Contenido` ocupa todo el espacio restante disponible después de la navegación y cabecera.

La composición interna de esta región cambia de acuerdo con la página representada.

---

### Composición estrecha

Cuando:

```text
ancho < 1024px
```

deja de utilizarse la estructura lateral de escritorio.

La estructura general pasa a ser:

En Início:

```text
Cabecera
Navegación móvil
Contenido  destacado
Actualizaciones de contenido
```

En demás páginas fuera del Início:

```text
Cabecera
Navegación móvil
Contenido
```

No se mantiene una navegación lateral reducida.

No se intenta conservar la estructura de escritorio mediante reducción proporcional de sus regiones.

La composición estrecha debe continuar reorganizándose correctamente hasta un ancho disponible de:

```text
320px CSS
```

para el contenido de desplazamiento vertical.

---

### Pie

El sitio no dispone de pie global.

El contenido termina cuando termina la página.

---

## Adaptación a diferentes pantallas

No consiste en reducir proporcionalmente la representación de escritorio.

Debe conservar:

```text
Contenido
Jerarquía
Identidad visual
Funciones
Estados
Orden editorial
```

y debe cambiar:

```text
Composición
Posición
Ancho disponible
Organización interna
Distribución de tarjetas
```

La misma adaptación responde tanto al ancho físico disponible como al ancho CSS resultante de la ampliación del navegador.

---

### Puntos de ruptura

La aplicación utiliza tres composiciones principales:

```text
ancho >= 1360px
=> escritorio amplio

1024px <= ancho < 1360px
=> escritorio intermedio

ancho < 1024px
=> composición estrecha
```

No se introduce una sucesión adicional de puntos de ruptura únicamente para cambiar cantidades fijas de columnas.

Los componentes que deben responder naturalmente al espacio disponible deben hacerlo sin depender de un número predeterminado de columnas.

No se crea un punto de ruptura adicional en `320px`.

La composición estrecha debe continuar funcionando hasta ese ancho.

---

### Tipografía

La escala de escritorio se utiliza cuando:

```text
ancho >= 1024px
```

La escala para pantallas estrechas se utiliza cuando:

```text
ancho < 1024px
```

No existe una tercera escala tipográfica para el escritorio intermedio.

No se utiliza escalado continuo entre las dos escalas.

Los tamaños se implementan mediante `rem` según [Escala tipográfica](./16-tipografia-y-espaciado.md#escala-tipográfica).

La raíz utiliza:

```css
font-size: 100%;
```

La configuración del usuario determina el tamaño efectivo de `1rem`.

La aplicación debe soportar un aumento del texto de:

```text
200%
```

sin pérdida de contenido ni funcionalidad.

---

### Espaciado

El padding horizontal general utiliza:

```text
ancho >= 1360px
=> 24px

1024px <= ancho < 1360px
=> 24px

ancho < 1024px
=> 16px
```

Permanecen definidos:

```text
padding de paneles         => 16px
gap entre tarjetas         => 16px
título / párrafo           => 12px
párrafo / párrafo          => 16px
secciones mayores          => 32px
grupos grandes             => 48px
altura mínima de controles => 48px
```

La composición estrecha no reduce automáticamente todos los espacios verticales.

No se utiliza `8px` como padding horizontal general de la aplicación.

Los valores anteriores corresponden a la presentación normal.

Cuando el usuario cambia el espaciado textual, los contenedores deben crecer o reorganizarse para conservar el contenido.

---

### Escritorio amplio

Cuando:

```text
ancho >= 1360px
```

Inicio utiliza:

```text
navegación => 224px
contenido  => 1fr
exposición => 320px
```

con:

```text
gap entre regiones => 24px
```

La columna principal conserva:

```text
mínimo => 720px
```

El ancho interior principal debe utilizar hasta:

```text
960px
```

El ancho máximo total previsto es:

```text
1504px
```

---

### Umbral de Inicio

La composición de tres regiones de Inicio requiere:

```text
24px
+ 224px
+ 24px
+ 720px
+ 24px
+ 320px
+ 24px
= 1360px
```

Por debajo de ese ancho no se intenta mantener simultáneamente:

```text
navegación de 224px
contenido mínimo de 720px
área de exposición de 320px
gaps y paddings correspondientes
```

---

### Escritorio intermedio

Cuando:

```text
1024px <= ancho < 1360px
```

la navegación sigue lateral y mantiene:

```text
224px
```

Las páginas internas siguen utilizando:

```text
navegación | contenido
```

Inicio deja de utilizar la columna lateral de Actualizaciones.

Actualizaciones pasa debajo del contenido destacado.

Conceptualmente:

```text
Navegación | Contenido

Contenido
|
+-- Proyectos destacados
+-- Artículos destacados
+-- Certificaciones destacadas
+-- Actualizaciones
```

Durante toda la composición de escritorio permanecen como valores normales mínimos:

```text
navegación lateral => 224px de ancho
cabecera expandida => 320px de altura mínima
cabecera compacta  => 112px de altura mínima
```

La navegación lateral no reduce progresivamente su ancho para intentar mantener la composición de escritorio amplio.

Las alturas de cabecera deben crecer cuando el contenido textual necesita más espacio.

---

### Composición estrecha

Cuando:

```text
ancho < 1024px
```

la estructura lateral deja de utilizarse.

La composición global es:

```text
Cabecera
Navegación móvil
Contenido
```

La aplicación no reproduce una versión reducida de la barra lateral.

Esta composición debe continuar funcionando hasta:

```text
320px CSS
```

sin pérdida de contenido ni funcionalidad y sin desplazamiento horizontal de la página para el contenido normal.

---

### Cabecera estrecha

La cabecera mantiene su identidad.

El estado expandido conserva:

```text
Fondo visual y foto juntos
Nombre
Descripción breve
```

El estado compacto conserva:

```text
Fondo visual y foto juntos
Nombre
```

La descripción breve no permanece visible en el estado compacto.

La fotografía:

```text
permanece visible
permanece integrada
mantiene proporciones
no utiliza formato circular
```

Los valores:

```text
320px
112px
```

constituyen alturas mínimas normales de escritorio.

No constituyen alturas máximas capaces de recortar texto.

En la composición estrecha, la altura deriva de:

```text
Contenido
Padding
Ancho disponible
Tamaño efectivo del texto
Espaciado efectivo del texto
```

---

### Barra de navegación estrecha

La barra aparece inmediatamente debajo de la cabecera.

Presenta:

```text
Menú | Idioma | Tema
```

Idioma y Tema no se ocultan dentro de Menú.

La barra sigue disponible durante el desplazamiento junto con la cabecera compacta.

Cuando la fila deja de caber correctamente por el ancho o por el tamaño del texto, la barra debe reorganizar sus controles sin ocultarlos.

Cada control independiente mantiene un objetivo interactivo mínimo de:

```text
48px x 48px CSS
```

La reorganización no reduce el objetivo para conservar artificialmente una única fila.

---

### Apertura del menú

Al activar `Menú`:

```text
Menú cerrado
        |
        V
Navegación expandida
```

La navegación aparece debajo de la barra dentro del flujo normal.

La apertura desplaza el contenido hacia abajo.

No se utiliza:

```text
drawer
overlay
panel lateral superpuesto
```

Al cerrar el menú, el contenido recupera el espacio correspondiente.

La apertura y el cierre requieren una activación explícita y no se producen solamente por pasar el puntero sobre el control.

---

### Grupos expandibles del menú

Cada grupo utiliza dos estados visuales.

Estado cerrado:

```text
IconChevronDown
```

Al activarlo:

```text
IconChevronDown
=> IconChevronUp

grupo
=> abierto
```

Solamente el grupo activado permanece abierto.

Estado abierto:

```text
IconChevronUp
```

Al activarlo nuevamente:

```text
IconChevronUp
=> IconChevronDown

grupo
=> cerrado
```

La operación afecta solamente al grupo.

No realiza navegación hacia un elemento.

La regla se aplica a todos los grupos expandibles de la navegación.

Si se activa más que uno grupo al mismo tiempo, uno no cerra al otro automaticamente.

El objetivo interactivo corresponde a toda la fila del grupo.

El icono no constituye un objetivo separado.

---

### Selección de un destino desde el menú

Cuando se selecciona un elemento concreto:

```text
elemento
=> navegar

grupo
=> cerrado
=> IconChevronDown

Menú
=> cerrado
```

Cuando se selecciona un acceso directo:

```text
destino
=> navegar

Menú
=> cerrado
```

La navegación expandida no permanece ocupando espacio después de seleccionar el destino.

Cuando la navegación produce una nueva página, el cierre del menú y del grupo precede al foco programático sobre el encabezado principal de la página de destino.

El comportamiento de foco se encuentra definido en [Cambio de página y foco](./24-accesibilidad.md#cambio-de-página-y-foco).

---

### Inicio en composición estrecha

El orden es:

```text
Cabecera
Navegación móvil
Proyectos destacados
Artículos destacados
Certificaciones destacadas
Actualizaciones
```

Actualizaciones deja de ser lateral.

Su contenido y su función permanecen iguales.

Las secciones destacadas conservan su orden editorial.

---

### Páginas internas en composición estrecha

La estructura global es:

```text
Cabecera
Navegación móvil
Contenido
```

Dentro de `Contenido`, un componente no se convierte obligatoriamente en vertical solamente porque la composición global sea estrecha.

Se utiliza:

```text
Horizontal y cabe correctamente
=> mantener

Horizontal y no cabe correctamente
=> reorganizar verticalmente
```

El crecimiento del texto forma parte de la comprobación de si la composición sigue cabiendo correctamente.

---

### Rejillas

Las rejillas no utilizan un número fijo de columnas.

La regla es:

```text
Presentar tantas tarjetas completas como permita el ancho disponible.

Cuando la siguiente tarjeta no cabe correctamente:
=> continuar en la fila siguiente.
```

No existe:

```text
mínimo fijo de columnas
máximo fijo de columnas
cantidad fijas de tarjetas por fila
```

El mínimo natural es una tarjeta por fila.

El tamaño efectivo del texto participa en el espacio necesario de cada tarjeta.

---

### Contenido ancho

La prioridad es:

```text
1. Reorganizar
2. Redimensionar proporcionalmente
3. Adaptar internamente
4. Desplazamiento horizontal propio cuando la estructura bidimensional sea necesaria
```

El desplazamiento horizontal de toda la página no se utiliza como solución para un componente interno.

El cuarto tratamiento se reserva para contenido cuya disposición bidimensional necesita conservarse para mantener su uso, comprensión o significado.

Si esta condición existe:

```text
componente concreto
=> overflow horizontal
```

No:

```text
Página completa
=> overflow horizontal
```

Una tabla, bloque de código, diagrama, gráfico u otro contenido ancho debe utilizar primero las alternativas anteriores cuando estas conservan correctamente su información.

El mecanismo de desplazamiento propio se deja bajo el comportamiento normal del navegador y no se convierte en una función personalizada cuyo único acceso requiera arrastre.

---

### Elementos visuales

Las imágenes, diagramas y demás elementos visuales utilizan el espacio disponible sin deformarse.

La regla general es:

```text
ancho necesario menor
=> redimensionar proporcionalmente
```

mientras el elemento continúe siendo legible.

Un elemento necesario no desaparece automáticamente por utilizar una pantalla estrecha, por ampliación ni por cambio de orientación.

---

### Botones

La altura mínima estándar es:

```text
48px
```

En escritorio, las acciones principales utilizan normalmente su ancho natural.

En composición estrecha, cuando forman parte del flujo principal:

```text
ancho => 100%
```

Los botones con contenido textual deben crecer verticalmente cuando el texto necesita más espacio.

La altura mínima de `48px` no constituye una altura máxima.

Los controles compactos de la navegación mantienen la geometría necesaria para constituir:

```text
Menú | Idioma | Tema
```

mientras la fila cabe correctamente.

Cuando deja de caber, la composición debe reorganizarse.

Los controles no se recortan para conservar artificialmente una sola fila.

Todo botón independiente mantiene como mínimo:

```text
48px x 48px CSS
```

de objetivo interactivo.

---

### Formulario

Los campos permanecen verticales y utilizan el ancho disponible.

El botón utiliza:

```text
ancho >= 1024px
=> ancho natural
=> altura mínima 48px
=> padding horizontal 24px
```

```text
ancho < 1024px
=> ancho 100%
=> altura mínima 48px
```

Durante `enviando...`, se conserva la misma regla de ancho y altura mínima.

Los campos y controles deben crecer cuando el texto o su espaciado necesitan más espacio.

Los campos de una línea mantienen como mínimo:

```text
altura => 48px
```

y todos los controles interactivos independientes del formulario mantienen el mínimo general de objetivo.

---

### Sobre mí

En escritorio debe mantenerse una composición horizontal entre texto y elemento visual mientras el contenido cabe correctamente.

Cuando la disposición horizontal deja de caber correctamente:

```text
elemento visual
texto
```

o el orden editorial definido para el bloque se presentan verticalmente.

El orden del bloque no se invierte automáticamente por su índice.

Los elementos visuales mantienen sus proporciones.

La misma reorganización se aplica cuando el aumento del texto hace que una composición anteriormente horizontal deje de caber.

---

### Proyecto

En escritorio debe mantenerse:

```text
imagen | panel de metadatos
```

cuando el espacio resulta adecuado.

Cuando deja de resultar adecuado:

```text
imagen
panel de metadatos
```

se presentan verticalmente.

El panel debe reorganizar también sus metadatos internamente.

La imagen se redimensiona proporcionalmente.

El redimensionamiento del texto participa en esta decisión de reorganización.

---

### Certificado y Certificación

En escritorio debe utilizarse una composición horizontal cuando el contenido cabe correctamente.

Cuando deja de caber, una Certificación utiliza conceptualmente:

```text
Imagen
Certificación
Nombre
Entidad
Fecha
Expiración
Código de credencial
Enlace de verificación
Volver a certificaciones
```

Cada región utiliza el ancho disponible.

La imagen mantiene sus proporciones.

Los valores:

```text
No expira
No disponible
```

se conservan cuando corresponden.

Un Certificado utiliza la misma adaptación sin incorporar campos que no pertenecen a su contrato.

El crecimiento del texto debe provocar esta reorganización antes de producir recorte o desplazamiento horizontal de la página.

---

### Artículo

En escritorio conserva el ancho de lectura definido mientras ese ancho sigue siendo compatible con el espacio disponible.

En composición estrecha utiliza el ancho disponible y:

```text
padding horizontal => 16px
```

El orden editorial no cambia.

Las tablas, bloques de código, diagramas, grafos, imágenes y otros contenidos anchos utilizan la prioridad general definida en [Contenido ancho](#contenido-ancho).

El texto debe refluir dentro del ancho disponible.

---

### Estados comunes

Los estados comunes utilizan la composición responsive correspondiente al ancho disponible.

Esto incluye:

```text
Skeleton
Estado vacío
Error de carga
Contenido no encontrado
Estados del formulario
```

Un estado no hace regresar la geometría de escritorio.

La unidad de presentación mantiene sus límites independientemente de la composición utilizada.

Los mensajes y controles de estado siguen las mismas reglas de redimensionamiento y reflujo que el contenido normal.

---

### Principio de conservación

Responsive debe cambiar:

```text
posición
disposición
ancho
cantidad natural de columnas
organización interna
altura necesaria para contenido textual
```

pero no cambia arbitrariamente:

```text
contenido
jerarquía
orden editorial
funciones
estados
identidad visual
```

La adaptación debe utilizar el espacio disponible para reorganizar la interfaz sin introducir una segunda versión conceptual del sitio.

---

### Redimensionamiento y reflujo

La interfaz debe conservar el contenido y la funcionalidad cuando el texto aumenta hasta:

```text
200%
```

La ampliación del navegador no debe estar restringida.

La aplicación utiliza la configuración de la ventana gráfica:

```html
<meta
    name="viewport"
    content="width=device-width, initial-scale=1"
>
```

No utiliza restricciones equivalentes a:

```text
user-scalable=no
maximum-scale=1
```

La reducción del ancho CSS provocada por la ampliación debe activar las mismas reglas responsive definidas para una ventana físicamente estrecha.

Para contenido de desplazamiento vertical, la aplicación debe funcionar con:

```text
ancho => 320px CSS
```

sin pérdida de información ni funcionalidad y sin exigir desplazamiento horizontal de la página.

Conceptualmente:

```text
1280px CSS
+ ampliación equivalente al 400%
=> 320px CSS disponibles
=> composición estrecha
=> reflujo completo
```

No se introduce una versión diferente de la interfaz para este caso.

Todo contenedor que incluye texto debe aumentar su dimensión necesaria cuando el redimensionamiento o el espaciado del texto requieren más espacio.

Una dimensión normal definida en esta especificación debe funcionar como dimensión mínima cuando contiene texto.

Conceptualmente:

```text
Dimensión normal
=> valor mínimo

Texto necesita más espacio
=> crecer o reorganizar

Resultado
=> contenido completo
=> funcionalidad completa
```

No debe producirse:

```text
Recorte
Truncamiento
Ocultación
Superposición
Pérdida de controles
Pérdida de acciones
Pérdida de información
```

Las cadenas extensas deben ajustarse dentro del contenedor cuando su división conserva el significado.

Cuando la división altera el significado o la estructura necesaria, el componente debe aplicar su tratamiento específico sin convertir toda la página en una superficie de desplazamiento horizontal.

---

### Orientación

La aplicación no exige una orientación concreta.

Debe funcionar completamente tanto en:

```text
orientación vertical
orientación horizontal
```

La orientación no determina por sí misma una composición.

El ancho y el espacio efectivo resultantes determinan cuál regla responsive se aplica.

Conceptualmente:

```text
Cambio de orientación
        |
        V
Cambiar espacio disponible
        |
        V
Evaluar composición responsive
        |
        V
Representar la misma funcionalidad
```

No se utiliza:

```text
Bloqueo de orientación
Mensaje obligatorio para girar el dispositivo
Contenido oculto por orientación
Función disponible solamente en orientación vertical
Función disponible solamente en orientación horizontal
```

No existe una excepción funcional del sitio que requiera una orientación específica.

El cambio de orientación no constituye por sí mismo una orden para ejecutar una función distinta de la reorganización de la interfaz.

---

## Puntos de ruptura

```text
>= 1360px
=> escritorio amplio

1024px–1359px
=> escritorio intermedio

< 1024px
=> composición estrecha

320px CSS
=> ancho mínimo de comprobación de reflujo para contenido vertical
```

---

## Layout de escritorio amplio

```text
Navegación       => 224px
Contenido        => 1fr
Exposición       => 320px
Gap principal    => 24px
Mínimo contenido => 720px
Máximo interior  => 960px
Máximo total     => 1504px
```

---

## Layout de escritorio intermedio

```text
Navegación => 224px
Contenido  => 1fr

Actualizaciones
=> debajo del contenido destacado
```

---

## Layout estrecho

```text
Cabecera
Navegación móvil
Contenido
```

```text
Navegación móvil
=> Menú | Idioma | Tema
```

---

## Redimensionamiento y reflujo

```text
Texto máximo de comprobación   => 200%
Raíz                           => font-size: 100%
Unidad tipográfica             => rem
Zoom                           => no restringido
Viewport                       => width=device-width, initial-scale=1
user-scalable=no               => no utilizar
maximum-scale=1                => no utilizar
Reflujo vertical               => 320px CSS
Página                         => sin desplazamiento horizontal para contenido normal
Contenedores textuales         => crecen o se reorganizan
Dimensiones normales con texto => valores mínimos
Orientación                    => vertical y horizontal
Bloqueo de orientación         => no utilizar
```

### Espaciado de texto

```text
Interlineado               => 1.5 veces el tamaño de fuente
Espacio después de párrafo => 2 veces el tamaño de fuente
Espaciado entre letras     => 0.12 veces el tamaño de fuente
Espaciado entre palabras   => 0.16 veces el tamaño de fuente
```

Estos valores corresponden a la comprobación de adaptación y no sustituyen los valores visuales normales.

---

Volver al índice [aquí](../README.md#índice-1).
