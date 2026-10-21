# 24. Accesibilidad

La accesibilidad forma parte de la estructura, la presentación y el comportamiento normal de la aplicación.

No constituye una representación paralela ni una segunda versión del sitio.

La misma interfaz debe proporcionar la información, jerarquía, relaciones, estados y mecanismos de interacción necesarios para su utilización mediante diferentes formas de acceso.

---

## Nivel de conformidad

La referencia de accesibilidad del proyecto es:

```text
WCAG 2.2
Nivel AA
```

El cumplimiento adicional de requisitos correspondientes al nivel AAA debe conservarse cuando resulte adecuado.

Alcanzar un requisito AAA concreto no convierte AAA en el nivel general de conformidad del proyecto.

Una combinación o comportamiento que no alcance AAA debe permanecer cuando cumple el requisito AA correspondiente.

Los criterios de nivel A siguen siendo obligatorios para la conformidad AA cuando no existe un criterio AA equivalente que sustituya la misma exigencia.

El nivel propio de un criterio de WCAG no se cambia para adaptarlo al nivel general del proyecto.

---

## Orden estructural y navegación mediante teclado

El orden visual, el orden del documento y el recorrido mediante teclado deben permanecer coherentes.

La presentación no utiliza reorganizaciones visuales que produzcan un orden diferente del orden semántico.

Conceptualmente:

```text
Orden visual
=> orden del DOM
=> orden normal de foco
```

Los controles interactivos deben utilizar elementos nativos cuando exista un elemento adecuado para su función.

El comportamiento nativo del teclado se conserva.

Los controles deben disponer de foco visible.

No se utilizan valores positivos de `tabindex` para reconstruir artificialmente un orden diferente.

La estructura correcta del documento tiene prioridad sobre el uso de `tabindex` cuando la estructura ya comporta lo mismo orden de lo visual.

`tabindex` solamente se utiliza cuando existe una necesidad concreta de foco que no queda resuelta mediante el comportamiento nativo.

El valor:

```html
tabindex="-1"
```

solamente debe utilizarse para permitir que un elemento reciba foco programáticamente sin incorporarlo al recorrido secuencial mediante `Tab`.

Este comportamiento se utiliza en el encabezado principal de una nueva página según [Cambio de página y foco](#cambio-de-página-y-foco).

Un elemento gráfico que forma parte de un control no constituye un segundo objetivo de foco cuando no dispone de una acción propia.

---

## Regiones semánticas y encabezados

La estructura principal utiliza las regiones semánticas correspondientes.

Conceptualmente:

```html
<header>
<nav>
<main>
```

Las regiones no reciben foco solamente por existir.

La jerarquía de encabezados corresponde a la jerarquía real del contenido.

Conceptualmente:

```text
H1
=> página actual

H2
=> secciones principales

H3
=> subsecciones

H4
=> nivel subordinado cuando existe
```

El nivel de encabezado no se selecciona a partir de su tamaño visual.

La carga inicial de una página no mueve automáticamente el foco hacia `main` ni hacia otro elemento únicamente para anunciar la página.

Esta regla corresponde a la carga inicial del sitio.

El cambio de una página por otra mediante navegación interna utiliza el comportamiento específico definido en [Cambio de página y foco](#cambio-de-página-y-foco).

La aplicación no incorpora un enlace adicional de salto al contenido principal.

La navegación entre regiones repetidas se apoya en la estructura semántica, los encabezados y la organización de la navegación.

---

## Grupos expandibles

Las secciones expandibles utilizan un único control para toda la fila interactiva.

El icono de expansión o contracción pertenece a ese mismo control.

No constituye un botón independiente.

El estado cerrado utiliza:

```text
IconChevronDown
aria-expanded="false"
```

El estado abierto utiliza:

```text
IconChevronUp
aria-expanded="true"
```

El control debe relacionarse con la región afectada mediante:

```text
aria-controls
```

El estado debe ser perceptible visualmente y estar disponible semánticamente.

El icono debe utilizar:

```text
aria-hidden="true"
```

cuando `aria-expanded` comunica el mismo estado a las tecnologías de asistencia.

Los elementos de un grupo cerrado no forman parte del recorrido mediante teclado mientras permanecen ocultos.

La misma regla se aplica a la navegación expandible utilizada en pantallas estrechas.

Cuando el menú está cerrado, sus elementos ocultos tampoco forman parte del recorrido mediante teclado.

El objetivo interactivo y el objetivo utilizado por las pruebas corresponde al control completo y no al elemento SVG interno.

El control completo mantiene el mínimo de:

```text
48px x 48px CSS
```

y su apertura o cierre requiere una activación explícita.

---

## Nombres accesibles de controles

Todo control dispone de un nombre accesible que comunica su función.

Cuando existe texto visible suficiente:

```text
texto visible
=> nombre del control
```

Si el control dispone además de una fuente explícita de nombre accesible, el nombre resultante debe contener el texto visible del control.

No se sustituye una etiqueta visible por un nombre accesible que utilice un texto diferente y deje de contener la información presentada visualmente.

El icono que acompaña a ese texto no se anuncia de forma independiente.

Cuando un control está formado solamente por un icono, dispone de un nombre accesible explícito y localizado.

Conceptualmente:

```text
Icono sin texto visible
=> nombre accesible que describe la acción
```

El nombre describe la función disponible y no solamente la apariencia gráfica del icono.

Los iconos decorativos o redundantes deben permanecer fuera del árbol de accesibilidad.

---

## Etiquetas y placeholders del formulario

Todos los campos visibles disponen de una etiqueta visible asociada estructuralmente al control.

La asociación utiliza:

```text
label
=> for
=> id del control
```

o la relación nativa equivalente.

Activar la etiqueta desplaza el foco al campo correspondiente.

El placeholder no sustituye la etiqueta.

Los placeholders definidos son:

```text
Nombre
=> Escriba su nombre

Apellido
=> Escriba su apellido

Dirección de correo electrónico
=> Escriba su dirección de correo electrónico

Motivo del contacto
=> Escriba el motivo del contacto

Mensaje
=> Escriba su mensaje
```

Una condición indispensable para completar correctamente un campo no debe existir solamente dentro del placeholder.

Cuando una instrucción necesita permanecer disponible después de comenzar la entrada, debe representarse mediante contenido persistente asociado al campo.

El placeholder utiliza en el tema claro:

```text
#676B72
```

En el tema oscuro utiliza:

```text
#8E97A3
```

El placeholder utiliza el mismo tamaño tipográfico del texto del campo:

```text
1rem
```

---

## Validación accesible de campos

Cuando un campo contiene un error de validación:

```text
campo
=> aria-invalid="true"
```

El mensaje de error visible se relaciona con el campo mediante:

```text
aria-describedby
```

o un mecanismo semántico equivalente.

El mensaje aparece junto al campo correspondiente.

El error debe comunicar la condición concreta que necesita corregirse.

Los valores introducidos permanecen disponibles.

La validación no mueve automáticamente el foco hacia cada campo inválido.

Los errores individuales de los campos no utilizan todos simultáneamente:

```text
role="alert"
```

La representación visible y la información suministrada a tecnologías de asistencia deben comunicar el mismo problema.

Cuando el error desaparece, el estado inválido y las relaciones asociadas se actualizan de acuerdo con el estado actual del campo.

---

## Mensajes generales del formulario

Los mensajes generales permanecen visibles mientras siguen siendo pertinentes.

No desaparecen automáticamente después de un período breve.

### Envío en curso

Durante una operación de envío, el formulario comunica que se encuentra ocupado mediante:

```html
<form aria-busy="true">
```

Cuando la operación finaliza:

```text
aria-busy="true"
=> aria-busy="false"
```

o el atributo deja de estar presente cuando ya no resulta necesario.

`aria-busy` se aplica al formulario como conjunto.

No se aplica individualmente a cada campo, porque la operación pendiente corresponde al envío del formulario completo.

Los campos textuales visibles pasan temporalmente al estado nativo:

```html
readonly
```

Conceptualmente:

```html
<input readonly>
```

```html
<textarea readonly></textarea>
```

No utilizan:

```html
disabled
```

durante el envío.

Los campos siguen formando parte del recorrido normal de foco y sus valores permanecen disponibles para las tecnologías de asistencia.

No se añade:

```text
aria-readonly="true"
```

cuando el control nativo ya utiliza `readonly`.

La semántica nativa constituye la fuente del estado de solo lectura.

El botón de envío conserva su elemento nativo:

```html
<button type="submit">
```

Durante la operación utiliza:

```html
<button type="submit" aria-disabled="true">
    enviando...
</button>
```

No utiliza:

```html
disabled
```

durante este estado.

El control permanece en el recorrido normal de foco.

El texto visible `enviando...` constituye también su nombre accesible durante la operación.

No se añade un `aria-label` diferente para sustituir ese texto.

`aria-disabled="true"` comunica que el control se encuentra temporalmente indisponible, pero no bloquea por sí mismo una nueva activación.

Por ese motivo, mientras la operación permanece pendiente, la lógica del frontend y del backend deben ambos impedir funcionalmente cualquier nuevo envío antes de crear una segunda solicitud.

Esta protección se aplica independientemente de que la nueva tentativa proceda de:

```text
Activación del botón
Teclado
Envío del formulario desde otro control
```

Conceptualmente:

```text
Operación pendiente
        |
        V
Nueva tentativa de envío
        |
        V
No iniciar segunda solicitud
```

El estado de progreso se anuncia mediante una región:

```html
<div role="status">
    enviando...
</div>
```

La región `role="status"` existe en el documento antes de comenzar la operación.

Al iniciar el envío, su contenido cambia para comunicar `enviando...`.

La comunicación es no interruptiva.

No recibe foco.

No se transforma el propio botón en una región de estado.

El botón conserva su semántica de botón.

La región utilizada para el anuncio de progreso permanece fuera del elemento:

```html
<form aria-busy="true">
```

Conceptualmente:

```html
<form aria-busy="true">
    ...
</form>

<div role="status">
    enviando...
</div>
```

Esta separación permite que el progreso se comunique mientras el formulario sigue marcado como ocupado.

La región de estado no introduce una segunda representación visual de `enviando...` mientras el texto ya se encuentra visible en el botón.

Debe permanecer visualmente oculta siempre que continúe disponible para las tecnologías de asistencia. Pero no debe ocultarse mediante un mecanismo que también la retire del árbol de accesibilidad.

El inicio de la operación no mueve el foco.

Cuando el envío se inicia desde el botón:

```text
Botón
=> conserva foco
```

Cuando el envío se inicia mediante teclado desde uno de los campos:

```text
Campo
=> pasa a readonly
=> conserva foco
```

No se mueve el foco hacia:

```text
role="status"
```

ni hacia otro elemento solamente para anunciar el progreso.

Cuando la solicitud termina, los estados temporales se restauran antes de representar el resultado final.

Conceptualmente:

```text
Formulario
=> aria-busy deja de indicar operación pendiente

Campos
=> quitar readonly

Botón
=> quitar aria-disabled
=> enviando... cambia a Enviar

Región de progreso
=> deja de anunciar enviando...
```

Después se representa el resultado correspondiente.

No se añade un mensaje independiente equivalente a:

```text
envío terminado.
```

porque el resultado final ya comunica el desenlace de la operación.

### Envío satisfactorio

El mensaje es:

```text
Mensaje enviado correctamente.
```

Utiliza:

```text
role="status"
```

La comunicación es no interruptiva.

No mueve el foco automáticamente.

### Límite de envíos

El mensaje es:

```text
Se alcanzó el límite de 5 envíos por hora.

Inténtelo de nuevo más tarde.
```

Utiliza:

```text
role="status"
```

La comunicación es no interruptiva.

No mueve el foco automáticamente.

### Fallo de envío

El mensaje es:

```text
No fue posible enviar el mensaje.

Inténtelo de nuevo.
```

Utiliza:

```text
role="alert"
```

La comunicación debe producirse cuando aparece el error.

No utiliza:

```text
alertdialog
```

No mueve el foco automáticamente.

Los mensajes correspondientes a cada campo permanecen separados de estos avisos generales.

---

## Estado accesible de los skeletons

Las formas internas del skeleton constituyen una representación visual.

No constituyen contenido accesible independiente.

Deben permanecer fuera del árbol de accesibilidad mediante:

```text
aria-hidden="true"
```

La unidad real cuyo contenido se encuentra pendiente comunica el estado de carga.

Mientras permanece pendiente:

```text
aria-busy="true"
```

Cuando la operación termina:

```text
aria-busy="false"
```

o el atributo deja de estar presente cuando ya no resulta necesario.

La carga de una unidad independiente no convierte toda la página en una única región ocupada.

Conceptualmente:

```text
Tarjeta pendiente
=> tarjeta ocupada

Página
=> no ocupada únicamente por esa tarjeta
```

Los skeletons no reciben foco.

No contienen controles ficticios.

No se añade un texto oculto equivalente a `Cargando...` solamente para crear una representación adicional destinada a tecnologías de asistencia.

La animación visual del skeleton permanece mientras la operación sigue pendiente.

Cuando la carga termina con contenido, vacío o error, el skeleton desaparece y la unidad adopta el estado correspondiente.

---

## Clasificación de imágenes

La alternativa textual depende de la función real de la imagen en su contexto.

La aplicación distingue entre:

```text
Imagen decorativa
Imagen informativa
Imagen funcional
Imagen de texto necesaria
Imagen compleja
Imagen relacionada con una experiencia sensorial específica
```

La clasificación no depende únicamente del archivo utilizado ni de su apariencia visual.

Una misma imagen debe necesitar un tratamiento diferente cuando cambia su función.

### Responsabilidad de las imágenes de contenido

Toda imagen que forme parte del contenido recibido por `sitio` dispone de:

```text
src
alt
```

`src` identifica el elemento visual.

`alt` contiene el valor final de la alternativa textual correspondiente a la representación solicitada.

Ambas propiedades son obligatorias cuando el contrato contiene una imagen.

`alt` utiliza siempre una cadena.

Debe contener texto cuando la imagen necesita una alternativa textual, o vacío cuando debe permanecer fuera de la información anunciada como imagen. No utiliza `null` y no se omite.

La responsabilidad se distribuye de la siguiente manera:

```text
sitio-api
=> conoce la representación solicitada
=> determina la función editorial de la imagen
=> proporciona src
=> proporciona el valor final de alt

sitio
=> representa src
=> representa exactamente el valor recibido en alt
```

`Sitio` no determina el valor de `alt` mediante la posición visual de la imagen.

No genera una alternativa a partir de:

```text
Nombre
Título
Descripción
Tipo de recurso
Dirección
Otros campos disponibles
```

No sustituye una alternativa recibida por otra.

No transforma por su cuenta un valor con texto en una alternativa vacía.

No transforma por su cuenta una alternativa vacía en texto.

Conceptualmente:

```html
<img src="{valor recibido}" alt="{valor recibido}">
```

### Sobre mí

Las imágenes de `Sobre mí` acompañan bloques de contenido y representan normalmente información relacionada con aquello que el bloque comunica.

Cuando la imagen aporta información propia:

```text
alt
=> descripción breve de la información visual relevante
```

La alternativa no necesita reproducir el título ni resumir todo el contenido del bloque.

Cuando la imagen constituye por sí misma la representación de una acción o un destino:

```text
alt
=> función o destino correspondiente
```

Cuando la imagen se encuentra dentro de un enlace que ya dispone de otro contenido suficiente para identificar su destino, la alternativa sigue correspondiendo a la función propia de la imagen.

Cuando la imagen no aporta información adicional, el valor de `alt` es vacío.

En todos los casos, `sitio-api` proporciona el valor final y `sitio` lo representa sin cambiarlo.

### Proyectos

Las imágenes de proyectos utilizan tratamientos diferentes entre las representaciones resumidas y el detalle.

En las tarjetas de proyectos de Inicio y de los listados ya se encuentran disponibles:

```text
Nombre
Descripción
Acción de acceso
```

La imagen funciona como apoyo visual redundante para la identificación del recurso.

Por lo tanto:

```text
Proyecto en representación resumida
=> alt=""
```

`Sitio-api` debe proporcionar la alternativa vacía en estos contratos resumidos.

En el detalle, la imagen principal constituye información propia del proyecto.

Debe representar, según el contenido:

```text
Interfaz
Resultado
Aspecto visual
Elemento relevante del proyecto
```

Por lo tanto:

```text
Proyecto en detalle
=> alt informativo
```

La alternativa describe brevemente la información visual relevante.

No se genera automáticamente a partir del nombre del proyecto.

El contenido editorial determina el valor y `sitio-api` lo proporciona en el contrato de detalle.

### Artículos

En las representaciones resumidas de artículos utilizadas en Inicio y en los listados ya se encuentran disponibles:

```text
Título
Descripción
Fecha
Acción de acceso
```

La imagen principal funciona como apoyo editorial.

Por lo tanto:

```text
Artículo en representación resumida
=> alt=""
```

`Sitio-api` proporciona la alternativa vacía para estas representaciones.

En el detalle del artículo, la imagen principal se clasifica de acuerdo con su función editorial concreta.

Cuando solamente funciona como portada y no añade información diferente del contenido textual:

```text
alt=""
```

Cuando aporta información propia necesaria para comprender aquello que se presenta:

```text
alt
=> alternativa informativa correspondiente
```

`Sitio` no decide entre estos estados.

El valor forma parte del contenido proporcionado para el artículo.

Las imágenes incluidas dentro del cuerpo Markdown se consideran individualmente.

Cada una debe disponer de la alternativa correspondiente a su propia función.

Conceptualmente:

```text
Imagen informativa
=> alternativa informativa

Imagen decorativa
=> alternativa vacía

Imagen funcional
=> función o destino

Imagen de texto necesaria
=> texto relevante

Imagen compleja
=> alternativa breve
=> descripción adicional

Imagen sensorial específica
=> identificación descriptiva correspondiente
```

La alternativa se define dentro del contenido editorial y llega al frontend a través del contenido procesado por `sitio-api`.

### Certificados y certificaciones

En las tarjetas de certificados y certificaciones ya se encuentran disponibles los datos necesarios para identificar cada recurso.

Según el tipo, esto incluye:

```text
Tipo
Nombre
Entidad
Fecha
Expiración
Acción de acceso
```

La imagen funciona como apoyo visual redundante en la representación resumida.

Por lo tanto:

```text
Certificado en representación resumida
=> alt=""

Certificación en representación resumida
=> alt=""
```

`Sitio-api` proporciona la alternativa vacía en estas representaciones.

En el detalle, la imagen representa el documento o credencial propiamente dicho.

Por lo tanto:

```text
Certificado en detalle
=> alt informativo

Certificación en detalle
=> alt informativo
```

La alternativa identifica brevemente el documento representado.

No necesita reproducir todos los datos que ya aparecen estructuralmente en la página.

La información extensa necesaria para comprender el documento no debe concentrarse únicamente dentro de `alt`.

Cuando existe información necesaria que no debe expresarse correctamente mediante una alternativa breve, esta debe formar parte del contenido textual accesible del detalle.

### Contactos

Las tarjetas de Contactos no utilizan imágenes de contenido para representar los medios disponibles.

Cada medio utiliza el icono definido por su tipo.

Por lo tanto, las reglas de `src` y `alt` para imágenes de contenido no se aplican a la representación visual de estas tarjetas.

El tratamiento accesible de los iconos se encuentra definido en [Iconos](#iconos).

---

## Imágenes decorativas

Las imágenes puramente decorativas no introducen información redundante.

Cuando corresponda, se implementan mediante recursos visuales de CSS.

Si una imagen decorativa necesita utilizar un elemento `<img>`, utiliza `alt=""`.

Na imagen que comunica información necesaria, no utiliza `background-image` como sustitución de una imagen accesible.

---

## Imágenes informativas

Una imagen informativa dispone de un texto alternativo que comunica la información esencial aportada por la imagen dentro de su contexto.

La alternativa no necesita describir cada detalle visual cuando esos detalles no forman parte de la información transmitida.

---

## Imágenes funcionales

Cuando una imagen forma parte de una acción o constituye la representación principal de una acción, su alternativa comunica la función o el destino correspondiente.

La alternativa no se limita a describir la apariencia del elemento visual.

---

## Imágenes de texto

Cuando resulta necesario utilizar una imagen que contiene texto y ese texto forma parte de la información que debe transmitirse, la alternativa incluye el contenido textual relevante.

---

## Imágenes complejas

Una imagen compleja debe disponer de una alternativa breve y de una descripción adicional cuando la información completa no debe expresarse adecuadamente mediante `alt`.

La alternativa breve permite identificar el contenido sin convertir el atributo en una descripción excesivamente extensa.

---

## Experiencias sensoriales específicas

Cuando la finalidad de una imagen incluye una experiencia visual o sensorial concreta y no constituye mera decoración, utiliza una identificación descriptiva compatible con esa función.

---

## Iconos

Cuando un icono acompaña a un texto visible que ya comunica completamente el significado:

```text
Icono
=> aria-hidden="true"

Texto
=> comunica el significado
```

Cuando un icono constituye por sí mismo un control, el control dispone de un nombre accesible localizado.

Cuando un icono representa visualmente un estado que también se encuentra comunicado mediante semántica propia del control, el icono no necesita anunciarse de forma independiente.

La exclusión del icono del árbol de accesibilidad no elimina su función visual.

Los iconos utilizados en las tarjetas de Contactos siguen estas mismas reglas.

Cuando el tipo de medio ya se encuentra identificado mediante texto visible suficiente, el icono funciona como apoyo visual y no se anuncia de forma independiente.

Cuando el icono pertenece a un control, su tamaño visual no limita la superficie interactiva del control.

---

## Fotografía de la cabecera

La fotografía personal de la cabecera constituye una imagen informativa relacionada con la identidad presentada.

Utiliza un elemento:

```html
<img>
```

No se implementa como `background-image`.

La alternativa conceptual corresponde a:

```text
Retrato de <nombre localizado>
```

La frase completa se localiza para el idioma correspondiente.

No se construye mediante concatenación de fragmentos que presupongan que todos los idiomas utilizan la misma estructura gramatical.

La representación localizada del nombre corresponde igualmente al idioma utilizado.

La misma función informativa se conserva en:

```text
Cabecera expandida
Cabecera compacta
Composición estrecha
```

El fondo visual que acompaña a la fotografía debe permanecer como decoración cuando no aporta información propia.

La fotografía de la cabecera pertenece a la estructura del sitio y utiliza la regla específica definida en esta sección.

No depende de los contratos de imágenes de contenido descritos en [Clasificación de imágenes](#clasificación-de-imágenes).

---

## Localización de información accesible

Los textos utilizados para proporcionar accesibilidad forman parte de la internacionalización del sitio.

Esto incluye, cuando corresponde:

```text
Alternativas textuales
Nombres accesibles
Placeholders
Instrucciones
Mensajes de validación
Mensajes de estado
Mensajes de error
Título del documento
```

No existe una segunda variante lingüística destinada exclusivamente a tecnologías de asistencia.

La información accesible utiliza el idioma correspondiente a la interfaz o al contenido al que pertenece.

Los nombres personales también utilizan la representación localizada establecida para el idioma correspondiente.

La localización debe cambiar el sistema de escritura utilizado para representar el nombre.

Las alternativas textuales que forman parte de contenido localizado son proporcionadas por `sitio-api` junto con la variante correspondiente del contenido.

Cuando una alternativa textual pertenece a una variante presentada en un idioma diferente del idioma principal del documento, debe quedar incluida dentro del contexto semántico del idioma correspondiente a esa variante.

---

## Idioma semántico

El idioma del documento y de las partes que utilizan un idioma diferente debe determinarse programáticamente.

Las etiquetas utilizadas corresponden al formato BCP 47 definido por la arquitectura lingüística del sitio.

La aplicación utiliza el atributo `lang` para declarar el idioma correspondiente.

### Criterios de conformidad

La aplicación utiliza los criterios de WCAG 2.2 correspondientes a la identificación semántica del idioma.

| Aspecto                        | Criterio                     | A      | AA        | AAA       |
| ------------------------------ | ---------------------------- | ------ | --------- | --------- |
| Idioma principal del documento | `3.1.1 Idioma de la página`  | cumple | No cumple | No cumple |
| Idioma de las partes           | `3.1.2 Idioma de las partes` | Cumple | Cumple    | No cumple |

No existe un criterio AA equivalente para la exigencia de idioma principal del documento, por lo que el criterio `3.1.1` conserva formalmente su nivel A.

No existe un criterio AAA adicional que imponga una declaración semántica superior de `lang` para el idioma principal o para los cambios de idioma. Se utiliza excepcionalmente dentro de la conformidad AA del proyecto porque no existe un criterio AA diferente que sustituya la declaración del idioma principal del documento.

El criterio `3.1.2` se aplica directamente en nivel AA a las partes cuyo idioma difiere del idioma principal.

La revisión de nivel AA sigue siendo la regla definida en esta sección.

### Idioma principal del documento

El idioma principal del documento corresponde al idioma activo del sistema.

Conceptualmente:

```html
<html lang="{idioma-activo}">
```

El valor utilizado debe ser una etiqueta BCP 47 válida correspondiente al idioma activo ya resuelto por `sitio`.

La secuencia inicial es:

```text
Resolver idioma activo
        |
        V
Establecer lang del documento
        |
        V
Presentar la aplicación
```

El documento no debe presentarse con una declaración lingüística correspondiente a una variante provisional diferente de la que finalmente se utiliza como idioma activo del sistema.

Cuando el usuario selecciona explícitamente otro idioma:

```text
Validar selección
        |
        V
Establecer nuevo idioma activo
        |
        V
Actualizar lang del documento
        |
        V
Representar la página equivalente
```

La navegación interna que conserva el idioma activo también conserva el valor de `lang` del documento.

Conceptualmente:

```text
Navegación interna
+ mismo idioma activo
=> mismo lang del documento
```

La utilización de un idioma de respaldo para una unidad de contenido no cambia el idioma principal del documento.

### Contenido en el mismo idioma del documento

Cuando el contenido utiliza el mismo idioma declarado por su ancestro, no necesita repetir el atributo `lang`.

Conceptualmente:

```text
Idioma del contenido
= idioma heredado
=> utilizar herencia normal
```

No se añaden declaraciones redundantes en cada elemento únicamente para repetir el mismo idioma.

### Contenido presentado mediante un idioma de respaldo

Cuando el idioma activo no está disponible para un contenido y la aplicación utiliza el idioma por defecto o el idioma original como respaldo, el idioma principal del documento sigue correspondiendo al idioma activo del sistema.

La región que pertenece a la variante efectivamente presentada utiliza su idioma real.

Conceptualmente:

```html
<html lang="{idioma-activo}">
    ...
    <article lang="{idioma-del-contenido}">
        ...
    </article>
</html>
```

La estructura concreta utilizada para agrupar el contenido depende del componente representado.

La declaración debe aplicarse a la región más adecuada que contenga exclusivamente el contenido perteneciente a esa variante.

No debe ampliarse a una región que incluya también textos propios de la interfaz en otro idioma.

Conceptualmente:

```text
Documento
=> idioma activo del sistema

Interfaz
=> idioma activo del sistema

Aviso de utilización de respaldo
=> idioma activo del sistema

Contenido presentado mediante respaldo
=> idioma real de la variante
```

La utilización del respaldo no cambia:

```text
Idioma activo
Preferencia almacenada
Dirección localizada
Navegación
Idioma de los mensajes de interfaz
lang del documento
```

### Unidades de contenido dentro de colecciones

Una colección debe contener simultáneamente recursos cuyas variantes efectivamente presentadas utilicen idiomas diferentes.

Cada unidad debe declarar su propio idioma cuando difiere del idioma heredado.

Conceptualmente:

```text
Colección
|
+-- Unidad A
|   => mismo idioma del documento
|   => hereda
|
+-- Unidad B
|   => idioma diferente
|   => declara lang propio
|
+-- Unidad C
    => otro idioma diferente
    => declara lang propio
```

No se asigna a toda la colección el idioma de una de sus unidades cuando esto produciría una declaración incorrecta para las demás.

Una tarjeta debe contener simultáneamente:

```text
Contenido del recurso
=> idioma de la variante presentada

Texto de acción
=> idioma activo de la interfaz
```

Por este motivo, cuando ambos idiomas son diferentes, `lang` debe aplicarse solamente a la parte que pertenece al contenido localizado.

Conceptualmente:

```html
<article>
    <div lang="{idioma-del-contenido}">
        <p> texto localizado de la interfaz </p>
    </div>
</article>
```

La estructura exacta debe variar según el componente, pero la separación lingüística debe conservar el mismo resultado semántico.

### Encabezados y alternativas textuales

Los encabezados que pertenecen al contenido utilizan el idioma de la variante que representan.

Cuando un encabezado principal corresponde a contenido presentado mediante un idioma de respaldo:

```text
H1
=> idioma real del contenido
```

Esto se mantiene también cuando el encabezado recibe foco programático después de una navegación interna.

Las alternativas textuales proporcionadas por `sitio-api` pertenecen igualmente al idioma de la variante de contenido correspondiente.

Cuando una imagen se encuentra dentro de una región que ya declara el idioma de la variante, su alternativa hereda ese contexto lingüístico.

Conceptualmente:

```html
<div lang="{idioma-del-contenido}">
    <img src="{camino-de-la-imagen}" alt="{texto-alternativo-localizado}">
</div>
```

No se cambia el texto de `alt` para adaptarlo al idioma del documento.

Se conserva la alternativa proporcionada por la variante correspondiente.

### Cambios de idioma dentro del contenido

Una variante debe contener deliberadamente una parte escrita en otro idioma.

Cuando el idioma de una parte difiere del idioma heredado y el cambio debe determinarse programáticamente, el elemento correspondiente declara su propio idioma.

Conceptualmente:

```html
<p lang="{idioma-de-la-parte}">
    ...
</p>
```

Cuando solamente una parte menor del elemento utiliza otro idioma:

```html
<span lang="{idioma-de-la-parte}">...</span>
```

El atributo debe aplicarse al elemento semántico más adecuado para representar el cambio.

No se introduce un elemento adicional únicamente por costumbre cuando un elemento semántico ya existente debe recibir correctamente la declaración.

No es necesario declarar un cambio lingüístico para los casos exceptuados por WCAG, como:

```text
Nombres propios
Términos técnicos
Palabras de idioma indeterminado
Palabras o expresiones que forman parte del uso habitual del idioma circundante
```

### Contenido procedente de Markdown

Los cambios lingüísticos definidos editorialmente dentro del contenido Markdown deben conservarse durante todo su procesamiento.

Conceptualmente:

```text
Contenido editorial
=> identifica cambio lingüístico cuando corresponde

sitio-api
=> procesa el contenido
=> conserva la información lingüística

sitio
=> representa el resultado
=> mantiene lang correspondiente
```

El frontend no analiza palabras, frases o párrafos para intentar detectar automáticamente su idioma.

La ausencia de una declaración editorial no se sustituye mediante detección heurística.

### Valores y herencia

Todo valor de `lang` establecido por la aplicación debe corresponder a una etiqueta BCP 47 válida.

Cuando el idioma ya se encuentra correctamente declarado por un ancestro:

```text
mismo idioma
=> heredar
=> no repetir lang innecesariamente
```

Cuando existe un cambio real de idioma:

```text
idioma diferente
=> declarar lang en la parte correspondiente
```

Cuando el idioma es conocido, no se utiliza `lang=""` para representar su valor.

La aplicación tampoco conserva una declaración antigua cuando el contenido cambia posteriormente a una variante de otro idioma.

La semántica debe corresponder siempre al contenido actualmente representado.

### Responsabilidades

No se añade una propiedad de idioma adicional al contrato general únicamente para establecer `lang` de una variante completa.

`Sitio` ya conoce:

```text
Idioma activo
Idioma solicitado
Idioma de la solicitud que produjo el contenido presentado
Idioma por defecto
Idioma original
Idiomas soportados
```

y debe utilizar esta información para aplicar el idioma semántico de la variante efectivamente representada.

Para los cambios lingüísticos internos de una variante, la información pertenece al propio contenido editorial y debe conservarse mediante `sitio-api`.

Conceptualmente:

```text
sitio-api
=> conserva la información lingüística editorial del contenido

sitio
=> conoce el idioma de la variante presentada
=> aplica el idioma semántico correspondiente
=> no detecta idiomas mediante análisis automático
```

---

## Método de cálculo de contraste

El contraste utiliza la luminancia relativa definida para WCAG.

Cada componente sRGB se normaliza:

```text
Csrgb = valor / 255
```

Después:

```text
si Csrgb <= 0.04045
=> C = Csrgb / 12.92

si Csrgb > 0.04045
=> C = ((Csrgb + 0.055) / 1.055) ^ 2.4
```

La luminancia relativa es:

```text
L = 0.2126R + 0.7152G + 0.0722B
```

El contraste se calcula mediante:

```text
(Lmás_claro + 0.05) / (Lmás_oscuro + 0.05)
```

El valor completo se utiliza para determinar conformidad.

No se redondea previamente para transformar un resultado inferior al umbral en un resultado conforme.

Para texto normal en nivel AA:

```text
contraste >= 4.5:1
```

Para texto grande en nivel AA:

```text
contraste >= 3:1
```

Para texto normal en nivel AAA:

```text
contraste >= 7:1
```

Para texto grande en nivel AAA:

```text
contraste >= 4.5:1
```

Los elementos no textuales necesarios para identificar componentes, estados o información gráfica utilizan el umbral aplicable de:

```text
contraste >= 3:1
```

No existe un umbral AAA adicional independiente para contraste no textual.

---

## Garantía cromática del tema claro

Los tokens del tema claro se definen de manera que su función pueda utilizarse en todos los contextos permitidos por el propio sistema sin depender de una comprobación manual diferente para cada página.

Las superficies claras consideradas para los colores generales son:

```text
Fondo principal       => #F6F3EE
Superficie primaria   => #FFFFFF
Superficie secundaria => #F1ECE5
Rojo suave            => #F7E9E8
Verde suave           => #E8F2EE
```

Los colores generales de texto deben mantener:

```text
>= 4.5:1
```

sobre cualquiera de estas superficies cuando su función permite ese uso.

El borde utilizado por el sistema debe mantener:

```text
>= 3:1
```

sobre cualquiera de estas superficies cuando representa una separación o componente que necesita ser percibido.

Las combinaciones específicas de un componente deben cumplir el requisito correspondiente dentro de las combinaciones que ese componente permite.

---

## Tokens accesibles del tema claro

Los valores definitivos son:

```text
Fondo principal       => #F6F3EE
Superficie primaria   => #FFFFFF
Superficie secundaria => #F1ECE5

Texto principal       => #141414
Texto secundario      => #5E6167
Texto tenue           => #676B72

Borde                 => #7A7E85

Rojo principal        => #B51E23
Rojo hover            => #99181C
Rojo suave            => #F7E9E8

Verde principal       => #2F6D59
Verde hover           => #255847
Verde suave           => #E8F2EE

Éxito                 => #2F6D59
Advertencia           => #8F6112
Error                 => #B51E23
Información           => #365E96

Focus color           => #141414
Placeholder           => #676B72
```

Los componentes utilizan:

```text
Botón principal
fondo normal => #B51E23
fondo hover  => #99181C
texto        => #FFFFFF

Botón secundario
fondo        => #FFFFFF
borde        => #7A7E85
texto        => #141414

Enlaces
normal       => #B51E23
hover        => #99181C
visited      => #7C3A65
```

---

## Auditoría de contraste del tema claro

Los colores generales fueron comprobados frente a todas las superficies en las que se permite su utilización.

La tabla registra el peor resultado encontrado entre las combinaciones permitidas.

| Elemento                              | Peor contraste comprobado | AA      | AAA        |
| ------------------------------------- | ------------------------: | ------- | ---------- |
| Texto principal `#141414`             |           `15.5939186510` | Cumple  | Cumple     |
| Texto secundario `#5E6167`            |            `5.2564684488` | Cumple  | No cumple  |
| Texto tenue `#676B72`                 |            `4.5313966803` | Cumple  | No cumple  |
| Borde `#7A7E85`                       |            `3.4512126340` | Cumple  | Cumple*    |
| Rojo principal `#B51E23`              |            `5.5991006265` | Cumple  | No cumple  |
| Rojo hover `#99181C`                  |            `7.1049041610` | Cumple  | Cumple     |
| Verde principal `#2F6D59`             |            `5.1485125447` | Cumple  | No cumple  |
| Verde hover `#255847`                 |            `6.9286169810` | Cumple  | No cumple  |
| Advertencia `#8F6112`                 |            `4.5736401147` | Cumple  | No cumple  |
| Información `#365E96`                 |            `5.5577743673` | Cumple  | No cumple  |
| Enlace visitado `#7C3A65`             |            `6.7073905201` | Cumple  | No cumple  |

También quedan comprobadas las combinaciones específicas principales:

| Combinación                                      | Contraste | AA      | AAA       |
| ------------------------------------------------ | --------: | ------- | --------- |
| Placeholder `#676B72` sobre `#FFFFFF`            |  `5.3534` | Cumple  | No cumple |
| `#FFFFFF` sobre rojo principal `#B51E23`         |  `6.6147` | Cumple  | No cumple |
| `#FFFFFF` sobre rojo hover `#99181C`             |  `8.3937` | Cumple  | Cumple    |
| Texto principal `#141414` sobre `#FFFFFF`        | `18.4225` | Cumple  | Cumple    |
| Borde `#7A7E85` sobre `#FFFFFF`                  |  `4.0772` | Cumple  | Cumple*   |
| Verde principal `#2F6D59` sobre `#E8F2EE`        |  `5.3197` | Cumple  | No cumple |
| Verde hover `#255847` sobre `#E8F2EE`            |  `7.1590` | Cumple  | Cumple    |

`Cumple*` indica que el elemento no textual satisface el requisito de contraste no textual aplicable. WCAG no incorpora un umbral AAA adicional independiente para este tipo de contraste.

Estas comprobaciones corresponden a los valores opacos indicados.

Si la representación efectiva cambia el color, debe comprobarse el resultado efectivo.

---

## Garantía cromática del tema oscuro

Los tokens del tema oscuro se definen de manera que cada función mantenga el nivel AA sobre todas las superficies en las que el sistema permite utilizarla.

Las superficies oscuras consideradas para los colores generales son:

```text
Fondo principal       => #0F141B
Superficie primaria   => #141B24
Superficie secundaria => #18212C
Rojo suave            => #3A1618
Verde suave           => #173328
```

Los colores de texto general deben mantener:

```text
>= 4.5:1
```

en todas las superficies sobre las que puedan aparecer.

Los elementos no textuales necesarios para identificar componentes o estados deben mantener:

```text
>= 3:1
```

respecto de la superficie adyacente correspondiente.

La comprobación de un token utiliza el peor resultado producido entre todas sus combinaciones permitidas.

Conceptualmente:

```text
Token
+ todas sus superficies permitidas
        |
        V
peor resultado
        |
        V
determina la conformidad
```

Los valores que solamente funcionan como superficies no necesitan satisfacer por sí mismos un umbral textual.

El requisito corresponde a la información situada sobre ellos.

El tema oscuro separa las funciones de rojo de primer plano y rojo de fondo.

Esta separación es necesaria porque los requisitos de:

```text
rojo como texto sobre superficie oscura
```

y:

```text
texto blanco sobre fondo rojo
```

requieren rangos de luminancia diferentes.

No debe reutilizarse el rojo de fondo como color general de texto ni el rojo interactivo como fondo del botón principal.

---

## Tokens accesibles del tema oscuro

Los valores definitivos son:

```text
Fondo principal       => #0F141B
Superficie primaria   => #141B24
Superficie secundaria => #18212C

Texto principal       => #F2F1EE
Texto secundario      => #B8BDC6
Texto tenue           => #8E97A3

Borde funcional       => #737B8B
Separador decorativo  => #202936

Rojo interactivo      => #FE6162
Rojo hover            => #FE686A
Rojo de fondo         => #D6363B
Rojo de fondo hover   => #C92F35
Rojo suave            => #3A1618

Verde principal       => #58B28D
Verde hover           => #4FA683
Verde suave           => #173328

Éxito                 => #58B28D
Advertencia           => #D6A34A
Error                 => #FE6162
Información           => #6FA8FF

Focus color           => #E2484D
Placeholder           => #8E97A3
Enlace visitado       => #BB7FD3

Casi negro            => #0A0E13
Blanco cálido         => #F7F5F1

Skeleton base         => #18212C
```

Los componentes utilizan:

```text
Botón principal
fondo normal => #D6363B
fondo hover  => #C92F35
texto        => #FFFFFF

Botón secundario
fondo        => transparent
borde        => #737B8B
texto        => #F2F1EE

Enlaces
normal       => #FE6162
hover        => #FE686A
visited      => #BB7FD3
focus        => #E2484D
```

---

## Auditoría de contraste del tema oscuro

Los colores del tema oscuro fueron comprobados según sus funciones y frente a todas las superficies en las que se permite su utilización.

Cuando un color debe aparecer en múltiples superficies, la tabla utiliza la combinación con menor contraste.

| Elemento                                    | Peor caso comprobado                                                   | Contraste         | AA      | AAA       |
| ------------------------------------------- | ---------------------------------------------------------------------- | ----------------: | ------- | --------- |
| Fondo principal `#0F141B`                   | Texto tenue `#8E97A3`                                                  | `6.2538873158:1`  | Cumple  | No cumple |
| Superficie primaria `#141B24`               | Texto tenue `#8E97A3`                                                  | `5.8627986079:1`  | Cumple  | No cumple |
| Superficie secundaria `#18212C`             | Texto tenue `#8E97A3`                                                  | `5.4965511091:1`  | Cumple  | No cumple |
| Texto principal `#F2F1EE`                   | sobre `#173328`                                                        | `12.0681208570:1` | Cumple  | Cumple    |
| Texto secundario `#B8BDC6`                  | sobre `#173328`                                                        | `7.2261022755:1`  | Cumple  | Cumple    |
| Texto tenue `#8E97A3`                       | sobre `#173328`                                                        | `4.6122661865:1`  | Cumple  | No cumple |
| Borde funcional `#737B8B`                   | sobre `#173328`                                                        | `3.2032708892:1`  | Cumple  | Cumple*   |
| Rojo interactivo `#FE6162`                  | sobre `#173328`                                                        | `4.6088541127:1`  | Cumple  | No cumple |
| Rojo interactivo hover `#FE686A`            | sobre `#173328`                                                        | `4.8048821419:1`  | Cumple  | No cumple |
| Verde principal `#58B28D`                   | sobre `#173328`                                                        | `5.3016380075:1`  | Cumple  | No cumple |
| Verde hover `#4FA683`                       | sobre `#173328`                                                        | `4.6181145990:1`  | Cumple  | No cumple |
| Advertencia `#D6A34A`                       | sobre `#173328`                                                        | `5.9697345002:1`  | Cumple  | No cumple |
| Información `#6FA8FF`                       | sobre `#173328`                                                        | `5.6607425863:1`  | Cumple  | No cumple |
| Foco `#E2484D`                              | sobre `#173328`                                                        | `3.4193508748:1`  | Cumple  | Cumple*   |
| Placeholder `#8E97A3`                       | sobre `#173328`                                                        | `4.6122661865:1`  | Cumple  | No cumple |
| Botón principal normal                      | `#FFFFFF` sobre `#D6363B`                                              | `4.7190498141:1`  | Cumple  | No cumple |
| Botón principal hover                       | `#FFFFFF` sobre `#C92F35`                                              | `5.3278994839:1`  | Cumple  | No cumple |
| Botón secundario, texto                     | `#F2F1EE` sobre `#18212C`                                              | `14.3818765872:1` | Cumple  | Cumple    |
| Botón secundario, borde                     | `#737B8B` contra `#18212C`                                             | `3.8174167420:1`  | Cumple  | Cumple*   |
| Enlace visitado `#BB7FD3`                   | sobre `#173328`                                                        | `4.6016656338:1`  | Cumple  | No cumple |
| Cabecera, nombre `#F2F1EE`                  | fotografía con capa negra mínima del `60%`; peor fondo `#666666`       | `5.0834876786:1`  | Cumple  | Cumple*   |
| Cabecera, descripción breve `#F2F1EE`       | fotografía con capa negra mínima del `60%`; peor fondo `#666666`       | `5.0834876786:1`  | Cumple  | No cumple |

`Cumple*` indica que el elemento no textual satisface el requisito de contraste no textual aplicable.

WCAG no incorpora un umbral AAA adicional independiente para contraste no textual.

El nombre de la cabecera satisface además el umbral AAA correspondiente a texto grande.

La descripción breve se evalúa como texto normal y no alcanza el umbral AAA de `7:1`.

La conformidad principal del proyecto permanece definida en AA.

---

## Contraste sobre la fotografía de la cabecera

La fotografía constituye un fondo variable y no debe considerarse equivalente a una superficie cromática fija.

En el tema oscuro, todo texto superpuesto a la imagen utiliza:

```text
#F2F1EE
```

La región completa situada detrás del texto incorpora:

```css
background: rgba(0, 0, 0, 0.60);
```

o un tratamiento visual equivalente que garantice como mínimo la misma reducción de luminosidad.

La capa debe formar parte de un gradiente.

Cuando se utiliza gradiente:

```text
área ocupada por el texto
=> opacidad negra >= 60%

área externa al texto
=> debe reducir progresivamente la opacidad
```

La capa no debe iniciar su reducción dentro del área real ocupada por el bloque textual.

La garantía no depende de una posición horizontal fija ni de un porcentaje fijo del ancho de la fotografía.

Depende del espacio ocupado por:

```text
Nombre
Descripción breve
```

en la composición activa.

El peor caso matemático supone:

```text
Fotografía original => #FFFFFF
Capa negra          => 60%
Fondo resultante    => #666666
Texto               => #F2F1EE
Contraste           => 5.0834876786:1
```

Por lo tanto:

```text
5.0834876786:1 >= 4.5:1
```

La combinación satisface AA para texto normal.

La garantía se conserva aunque la fotografía sea sustituida posteriormente por otra imagen más luminosa.

No debe dependerse de inspeccionar visualmente una fotografía concreta para determinar si el texto resulta legible.

Cuando el texto aumenta de tamaño o de espaciado, el área protegida por la capa debe acompañar el tamaño real del bloque textual.

---

## Bordes y separadores

El tema claro utiliza:

```text
Borde => #7A7E85
```

como token único para las líneas que deben mantener contraste suficiente.

No existen valores independientes de menor contraste para:

```text
Borde estructural
Borde de control
Separador
```

cuando esas líneas necesitan ser perceptibles.

El grosor sigue dependiendo de la función visual definida en [Bordes](./17-sombras-y-bordes.md#bordes).

El tema oscuro utiliza:

```text
Borde funcional      => #737B8B
Separador decorativo => #202936
```

El borde funcional se utiliza cuando la línea participa en la identificación de:

```text
Control
Componente
Estado
Separación estructural necesaria
```

El separador decorativo solamente debe utilizarse cuando su ausencia no elimina información necesaria.

Conceptualmente:

```text
Línea necesaria
=> #737B8B

Línea puramente decorativa
=> #202936
```

Una línea inicialmente decorativa que pase a desempeñar una función necesaria debe cambiar al tratamiento funcional.

El cambio de tema no cambia el significado de la línea.

---

## Foco visible

El indicador general utiliza:

```css
outline: 2px solid var(--focus-color);
outline-offset: 2px;
```

En el tema claro:

```text
--focus-color => #141414
```

En el tema oscuro:

```text
--focus-color => #E2484D
```

En el peor caso permitido del tema oscuro:

```text
#E2484D sobre #173328
=> 3.4193508748:1
```

El indicador satisface el requisito de contraste no textual aplicable.

El foco debe permanecer perceptible sobre las superficies en las que debe aparecer.

No utiliza `currentColor` como regla general para permitir que cada control produzca un resultado de contraste diferente.

El indicador debe coexistir con estados como:

```text
Activo
Seleccionado
Error
Advertencia
```

sin sustituir el significado propio de esos estados.

El foco identifica qué control se encuentra actualmente enfocado.

Los demás estados siguen comunicando su propio significado.

---

## Estados semánticos y color

Los colores semánticos no constituyen el único medio para comunicar información.

Conceptualmente:

```text
Color
+ texto o información equivalente
+ estructura técnica correspondiente
=> significado del estado
```

Esto se aplica a:

```text
Éxito
Advertencia
Error
Información
```

y a los demás estados necesarios para utilizar la aplicación.

El estado debe continuar siendo comprensible cuando el color no debe distinguirse.

Los valores semánticos del tema oscuro son:

```text
Éxito       => #58B28D
Advertencia => #D6A34A
Error       => #FE6162
Información => #6FA8FF
```

Todos ellos mantienen AA sobre las superficies permitidas para su función.

---

## Enlaces

Los enlaces deben disponer de semántica de enlace y de una identificación visible suficiente.

Un enlace situado dentro de texto corrido no se diferencia únicamente mediante color.

Utiliza subrayado u otra señal visual equivalente que permita reconocerlo independientemente de la percepción cromática.

Los enlaces utilizados como acciones aisladas tampoco dependen exclusivamente del color ni únicamente del contexto de la composición.

Deben disponer de texto, tratamiento visual y estructura técnica que permitan reconocer su función interactiva.

El texto del enlace debe comunicar adecuadamente su destino o acción.

En el tema claro:

```text
normal  => #B51E23
hover   => #99181C
visited => #7C3A65
focus   => #141414
```

En el tema oscuro:

```text
normal  => #FE6162
hover   => #FE686A
visited => #BB7FD3
focus   => #E2484D
```

Los estados:

```text
normal
hover
visited
focus
```

deben conservar el contraste correspondiente en las combinaciones permitidas.

El estado `hover` solamente constituye retroalimentación visual.

El enlace sigue siendo reconocible y utilizable sin que ese estado exista.

Un enlace que constituye una acción independiente utiliza el objetivo mínimo definido en [Objetivos interactivos](./15-iconos-y-controles.md#objetivos-interactivos).

Un enlace situado dentro de un bloque de texto conserva su presentación textual y utiliza la excepción normativa aplicable a objetivos integrados en texto.

---

## Colores efectivos

La validación corresponde al color realmente representado.

Los valores comprobados no deben considerarse automáticamente válidos cuando se cambian mediante:

```text
opacity
rgba
superposición
gradiente
composición sobre fotografía
otra mezcla visual
```

Conceptualmente:

```text
Token sin cambio
=> conserva el resultado comprobado

Color efectivo cambiado
=> requiere comprobar el resultado efectivo
```

La comprobación debe utilizar el fondo efectivo sobre el que se representa el elemento.

La fotografía de la cabecera utiliza la excepción controlada definida en [Contraste sobre la fotografía de la cabecera](#contraste-sobre-la-fotografía-de-la-cabecera), donde el resultado efectivo se garantiza mediante la capa mínima establecida.

---

## Título del documento

Cada página dispone de un `<title>` que describe su contenido o propósito.

Durante la navegación interna de Angular, el título se actualiza para corresponder a la página activa aunque no se produzca una carga completa de un nuevo documento HTML.

El título también se actualiza cuando cambia el idioma.

La identificación general del sitio es localizada y responde conceptualmente a:

```text
Portafolio de <nombre localizado>
```

La representación del nombre personal también corresponde al idioma activo.

La página inicial utiliza:

```text
<nombre localizado del sitio>
```

Las páginas internas utilizan:

```text
<título localizado de la página> | <nombre localizado del sitio>
```

Los recursos individuales utilizan:

```text
<nombre o título localizado del recurso> | <nombre localizado del sitio>
```

La información específica aparece antes de la identificación general del sitio.

Conceptualmente:

```html
<title>título específico | nombre del sitio</title>
```

El separador forma parte de la convención definida para el sitio y no cambia la jerarquía de la información.

---

## Cambio de página y foco

La carga inicial del sitio y la navegación interna entre páginas utilizan comportamientos de foco diferentes.

La aplicación no desplaza el foco solamente porque Angular haya creado una región, actualizado un componente o terminado una operación de carga. El movimiento programático se utiliza específicamente cuando una navegación interna sustituye una página conceptual por otra.

### Carga inicial

Durante el acceso inicial al sitio:

```text
Carga inicial
=> conservar comportamiento normal del navegador
=> no mover foco programáticamente
```

La existencia de:

```html
<main>
```

o de:

```html
<h1>
```

no produce por sí misma un movimiento de foco.

La carga inicial no intenta reproducir programáticamente un comportamiento que ya corresponde al inicio normal de un documento.

### Navegación interna hacia una nueva página

Una navegación interna constituye un cambio de página cuando el enrutamiento sustituye el contenido principal actual por otra página conceptual de la aplicación.

El cambio de la dirección por sí solo no determina esta condición.

Un cambio que conserva la misma página conceptual no debe provocar el movimiento definido para una nueva página.

La secuencia general es:

```text
Activar un destino interno
        |
        V
Navegación de Angular
        |
        V
Nueva página confirmada
        |
        +-- actualizar <title>
        |
        +-- representar la nueva página
        |
        +-- disponer del H1 correspondiente
        |
        V
Mover foco al H1
```

El foco solamente se desplaza cuando el encabezado principal de la nueva página ya existe y representa correctamente el destino alcanzado.

No se mueve el foco hacia un skeleton que represente provisionalmente un encabezado todavía no disponible.

Cuando el texto del encabezado depende del contenido solicitado, el movimiento ocurre después de que ese encabezado pueda representarse con su contenido correspondiente.

Cuando ese encabezado pertenece a una variante presentada mediante un idioma de respaldo, debe conservar además el idioma semántico definido en [Idioma semántico](#idioma-semántico).

### Encabezado principal enfocable

El encabezado principal de una página utiliza:

```html
<h1 tabindex="-1">...</h1>
```

solamente cuando necesita recibir el foco después de una navegación interna.

`tabindex="-1"` permite:

```text
Foco programático
=> permitido

Recorrido normal mediante Tab
=> no incorpora el H1 como parada adicional
```

El encabezado no se transforma en un control interactivo.

Su función sigue siendo representar semánticamente el encabezado principal de la página.

Después de recibir el foco, la navegación secuencial posterior sigue mediante los elementos interactivos siguientes de acuerdo con el orden normal del documento.

No se utilizan valores positivos de `tabindex` para colocar el encabezado dentro de una posición artificial de la secuencia.

### Región principal

La región:

```html
<main>
```

sigue delimitando semánticamente el contenido principal.

No recibe foco únicamente como consecuencia de una navegación interna.

La relación es:

```text
<title>
=> identifica el documento o página

H1
=> identifica el contenido principal de la página
=> recibe foco después del cambio interno de página

main
=> delimita la región principal
=> no constituye el destino automático de foco
```

### Actualizaciones dentro de una misma página

No producen un movimiento programático al `H1`:

```text
Carga o sustitución de datos dentro de la página actual
Finalización de un skeleton
Aparición de un estado vacío dentro de una unidad
Aparición de un error dentro de una unidad
Apertura de un grupo expandible
Cierre de un grupo expandible
Cambio de tema
Cambio de dirección que no sustituye la página conceptual
```

Los estados del formulario mantienen las reglas específicas definidas para sus mensajes y validación.

La actualización de una unidad independiente no convierte la operación en una nueva página.

Conceptualmente:

```text
Misma página
+ contenido actualizado
=> conservar foco

Nueva página
=> foco en H1
```

### Contenido no encontrado

Un resultado de contenido no encontrado constituye una página cuando es el destino final de una navegación.

Cuando se alcanza mediante navegación interna, su encabezado principal recibe el mismo tratamiento.

Conceptualmente:

```text
Navegación interna
        |
        V
Página no encontrada
        |
        V
H1 de la página
=> foco
```

No se mantiene el foco en el enlace o control que pertenecía a la página anterior.

### Navegación en pantallas estrechas

Cuando un destino se selecciona desde el menú de una composición estrecha:

```text
Seleccionar destino
        |
        V
Navegar
        |
        +-- cerrar grupo cuando corresponda
        |
        +-- cerrar Menú
        |
        V
Representar nueva página
        |
        V
Mover foco al H1
```

El cierre de la navegación expandida ocurre antes de situar el foco en la nueva página.

De esta manera, el foco no permanece asociado a un control perteneciente a una representación del menú que dejó de estar disponible.

### Anuncio del cambio de contexto

No se incorpora una región adicional:

```text
aria-live
```

ni un aviso independiente equivalente a:

```text
Página cambiada
```

solamente para anunciar la navegación.

El contexto se proporciona mediante:

```text
<title>
=> identificación general de la página

H1 enfocado
=> contexto inmediato del contenido representado
```

El encabezado principal localizado proporciona a las tecnologías de asistencia el nombre de la nueva página cuando recibe el foco.

No se repite esta información mediante una segunda región de anuncios cuando el cambio ya queda comunicado por el propio destino del foco.

---

## Redimensionamiento, reflujo, espaciado y orientación

La aplicación debe conservar contenido, información y funcionalidad durante el redimensionamiento del texto, la ampliación del navegador, el reflujo, la cambiación del espaciado textual y los cambios de orientación.

### Criterios de conformidad

Las decisiones de esta sección corresponden a los siguientes criterios de WCAG 2.2:

| Aspecto                      | Criterio                               | AA     | AAA       |
| ---------------------------- | -------------------------------------- | ------ | --------- |
| Orientación                  | `1.3.4 Orientación`                    | Cumple | No Cumple |
| Redimensionamiento del texto | `1.4.4 Redimensionamiento del texto`   | Cumple | No Cumple |
| Reflujo                      | `1.4.10 Reflujo`                       | Cumple | No Cumple |
| Espaciado del texto          | `1.4.12 Espaciado del texto`           | Cumple | No Cumple |
| Presentación visual          | `1.4.8 Presentación visual`            | Cumple | Cumple    |

Todo el sitio funciona sin exigir una orientación concreta.

El texto aumenta hasta `200%` sin pérdida de contenido ni funcionalidad.

El contenido de desplazamiento vertical funciona a `320px CSS` sin desplazamiento horizontal de página.

Los valores exigidos deben aplicarse sin pérdida de contenido ni funcionalidad.

Presentación visual relacionado; no se declara cumplimiento completo mediante las decisiones de esta sección.

El criterio `1.4.8` se revisa como referencia de nivel AAA, pero no debe declararse cumplido únicamente por satisfacer el redimensionamiento y el reflujo definidos aquí.

---

### Escala tipográfica relativa

La implementación tipográfica utiliza:

```css
html {
    font-size: 100%;
}
```

La aplicación no sustituye la preferencia de tamaño raíz del usuario mediante un valor absoluto.

El cuerpo utiliza:

```css
body {
    font-size: 1rem;
}
```

Los controles nativos heredan la tipografía correspondiente:

```css
button,
input,
textarea,
select {
    font: inherit;
}
```

Las escalas completas son las definidas en [Escala tipográfica](./16-tipografia-y-espaciado.md#escala-tipográfica).

Con una raíz equivalente a `16px`, las conversiones son:

```text
4rem     => 64px
3rem     => 48px
2.5rem   => 40px
2.25rem  => 36px
2rem     => 32px
1.75rem  => 28px
1.5rem   => 24px
1.375rem => 22px
1.25rem  => 20px
1.125rem => 18px
1rem     => 16px
0.875rem => 14px
0.75rem  => 12px
```

Los valores en píxeles de esta relación solamente expresan la equivalencia visual de referencia.

El tamaño efectivo sigue derivando de `rem`.

---

### Redimensionamiento del texto

El texto debe aumentar hasta:

```text
200%
```

sin pérdida de contenido ni funcionalidad.

La comprobación incluye:

```text
Nombre principal
Encabezados
Párrafos
Navegación
Subelementos de navegación
Botones
Selectores textuales
Campos
Placeholders
Etiquetas
Instrucciones
Errores
Mensajes de estado
Acciones
Metadatos
Fechas
Contenido Markdown
```

Todo contenedor que incluya texto debe crecer cuando el texto necesita más espacio.

Las dimensiones normales definidas para elementos textuales funcionan como dimensiones mínimas.

Conceptualmente:

```text
Ítem principal de navegación
=> min-height: 48px

Subítem de navegación
=> min-height: 48px

Botón principal
=> min-height: 48px

Botón secundario
=> min-height: 48px

Selector de idioma
=> min-height: 48px

Cabecera expandida de escritorio
=> min-height: 320px

Cabecera compacta de escritorio
=> min-height: 112px
```

Cuando el contenido necesita más espacio:

```text
altura efectiva
=> aumenta

ancho efectivo
=> aumenta cuando la composición lo admite

composición
=> se reorganiza cuando el ancho ya no resulta suficiente
```

No debe utilizarse:

```text
overflow oculto para eliminar texto
ellipsis para sustituir contenido necesario
altura máxima que recorte texto
superposición deliberada
reducción automática del texto para hacerlo caber
```

como solución al redimensionamiento.

El selector de tema constituye un control iconográfico y conserva:

```text
48px x 48px
```

mientras no incorpore texto visible dentro del propio control.

---

### Zoom del navegador

La aplicación no debe restringir la ampliación realizada mediante el navegador.

La configuración de la ventana gráfica utiliza:

```html
<meta
    name="viewport"
    content="width=device-width, initial-scale=1"
>
```

No utiliza:

```text
user-scalable=no
maximum-scale=1
```

ni otra restricción equivalente que impida la ampliación.

El zoom que reduce el ancho CSS disponible debe provocar la misma adaptación estructural que una ventana físicamente más estrecha.

Conceptualmente:

```text
Zoom aumenta
        |
        V
Ancho CSS disponible disminuye
        |
        V
Puntos de ruptura existentes
        |
        V
Composición responsive correspondiente
```

No existe un tratamiento paralelo específico para zoom.

---

### Reflujo

El contenido principal de la aplicación utiliza desplazamiento vertical.

Debe funcionar con un ancho de:

```text
320px CSS
```

sin pérdida de:

```text
Contenido
Información
Controles
Funciones
Estados
Acciones
Navegación
```

y sin exigir desplazamiento horizontal de toda la página.

La comprobación incluye el caso equivalente de:

```text
ventana de 1280px CSS
+ ampliación del 400%
=> 320px CSS disponibles
```

La aplicación no incorpora un punto de ruptura específico en `320px`.

La composición estrecha definida por debajo de `1024px` debe continuar reorganizándose correctamente hasta ese ancho.

Conceptualmente:

```text
ancho >= 1024px
=> composición de escritorio correspondiente

ancho < 1024px
=> composición estrecha

ancho = 320px CSS
=> composición estrecha
=> contenido completo
=> funcionalidad completa
=> sin desplazamiento horizontal de página
```

Las rejillas deben reducir naturalmente su cantidad de columnas hasta:

```text
1 tarjeta por fila
```

cuando ese es el único número que cabe correctamente.

Los componentes horizontales deben reorganizarse verticalmente cuando dejan de caber.

Los controles de navegación estrecha deben reorganizarse cuando ya no caben en una sola fila.

---

### Excepciones de desplazamiento horizontal

El desplazamiento horizontal propio se reserva para contenido cuya estructura bidimensional necesita conservarse para mantener:

```text
Uso
Comprensión
Significado
```

Conceptualmente:

```text
Contenido normal
=> reflujo
=> sin desplazamiento horizontal de página

Contenido ancho adaptable
=> reorganizar
=> redimensionar
=> adaptar internamente

Contenido bidimensional necesario
=> desplazamiento horizontal propio del componente
```

La excepción no se determina por el nombre del componente.

Por lo tanto:

```text
Tabla
=> adaptar cuando la adaptación conserva la información
=> desplazamiento interno solamente cuando necesita preservar la relación bidimensional

Código
=> ajustar líneas cuando el ajuste conserva el significado
=> desplazamiento interno cuando la estructura o indentación necesita preservarse

Diagrama o gráfico
=> redimensionar o adaptar cuando sigue legible
=> desplazamiento interno cuando necesita preservar su relación espacial
```

El componente exceptuado no debe provocar:

```text
overflow horizontal de la página completa
```

---

### Cadenas extensas

Las cadenas textuales que admiten división deben ajustarse al ancho disponible.

Esto se aplica a:

```text
Títulos
Nombres de recursos
Metadatos
Direcciones
Enlaces visibles
Identificadores presentados
Mensajes
Errores
Contenido recibido
```

Conceptualmente:

```text
Cadena divisible
=> envolver o dividir dentro del contenedor

Cadena cuya división cambia el significado
=> tratamiento específico del componente
```

Una cadena extensa no debe producir desplazamiento horizontal de toda la página cuando su división conserva correctamente la información.

---

### Espaciado del texto

La aplicación debe soportar simultáneamente los valores de prueba establecidos para `1.4.12 Espaciado del texto`.

Estos valores son:

```text
Interlineado
=> al menos 1.5 veces el tamaño de fuente

Espacio después de párrafos
=> al menos 2 veces el tamaño de fuente

Espaciado entre letras
=> al menos 0.12 veces el tamaño de fuente

Espaciado entre palabras
=> al menos 0.16 veces el tamaño de fuente
```

Estos valores no sustituyen los valores visuales normales definidos en [Alturas de línea](./16-tipografia-y-espaciado.md#alturas-de-línea) ni en [Espaciado](./16-tipografia-y-espaciado.md#espaciado).

Representan cambios que la interfaz debe soportar sin pérdida.

Cuando se aplican simultáneamente:

```text
Contenido
=> permanece completo

Funcionalidad
=> permanece completa

Contenedores
=> crecen cuando resulta necesario

Composición
=> se reorganiza cuando resulta necesario
```

No debe producirse:

```text
Texto recortado
Texto oculto
Superposición
Pérdida de controles
Pérdida de etiquetas
Pérdida de mensajes
Pérdida de acciones
```

Las alturas mínimas definidas para componentes textuales siguen funcionando como valores mínimos y no como límites máximos.

---

### Orientación

La aplicación no restringe el contenido a una orientación específica.

Debe funcionar completamente en:

```text
vertical
horizontal
```

No existe una función de `sitio` cuya utilización requiera una excepción basada en orientación.

No se utiliza:

```text
bloqueo de orientación
requisito de girar el dispositivo
mensaje que impida continuar hasta cambiar la orientación
contenido exclusivo de una orientación
funcionalidad exclusiva de una orientación
```

Cuando cambia la orientación:

```text
Orientación
=> cambia dimensiones disponibles

Dimensiones disponibles
=> determinan composición responsive

Composición
=> conserva contenido y funcionalidad
```

La interfaz no utiliza la orientación como sustituto de las reglas basadas en espacio disponible.

---

### Relación con el nivel AAA

El criterio:

```text
1.4.8 Presentación visual
=> nivel AAA
```

contiene requisitos adicionales relacionados con la presentación de bloques de texto.

Las decisiones de esta sección satisfacen aspectos relacionados con el redimensionamiento y el reflujo, pero no constituyen por sí solas una verificación completa de todos los requisitos de `1.4.8`.

Por lo tanto:

```text
1.4.8
=> relacionado
=> no declarar cumplimiento completo todavía
```

La evaluación AAA debe realizarse sobre todas las condiciones del criterio antes de registrarlo como cumplido, pero el nivel AA sigue siendo el requisito.

---

## Interacción por puntero y tacto

La interacción mediante puntero forma parte de la misma interfaz utilizada mediante teclado.

La aplicación no mantiene una versión funcional separada para ratón, pantalla táctil o lápiz.

Los controles propios deben conservar la misma función independientemente del mecanismo de entrada compatible utilizado.

### Criterios de conformidad

Las decisiones de esta sección corresponden a los siguientes criterios de WCAG 2.2:

| Aspecto                             | Criterio                                             | A      | AA        | AAA       |
| ----------------------------------- | ---------------------------------------------------- | ------ | --------- | --------- |
| Contenido al pasar el puntero o foco| `1.4.13 Contenido señalado con el puntero o en foco` | Cumple | Cumple    | No cumple |
| Gestos del puntero                  | `2.5.1 Gestos del puntero`                           | Cumple | No cumple | No cumple |
| Cancelación del puntero             | `2.5.2 Cancelación del puntero`                      | Cumple | No cumple | No cumple |
| Etiqueta en el nombre               | `2.5.3 Etiqueta en el nombre`                        | Cumple | No Cumple | No cumple |
| Actuación mediante movimiento       | `2.5.4 Actuación mediante movimiento`                | Cumple | No cumple | No cumple |
| Tamaño del objetivo mejorado        | `2.5.5 Tamaño del objetivo (mejorado)`               | Cumple | Cumple    | Cumple    |
| Mecanismos de entrada concurrentes  | `2.5.6 Mecanismos de entrada concurrentes`           | Cumple | Cumple    | Cumple    |
| Movimientos de arrastre             | `2.5.7 Movimientos de arrastre`                      | Cumple | Cumple    | No cumple |
| Tamaño mínimo del objetivo          | `2.5.8 Tamaño del objetivo (mínimo)`                 | Cumple | Cumple    | No cumple |

Los criterios:

```text
2.5.1
2.5.2
2.5.3
2.5.4
```

conservan formalmente el nivel A porque no existe un criterio AA equivalente que sustituya cada una de estas exigencias. Pero, el cumplimiento del proyecto sigue siendo obligatorio para la conformidad AA general.

Los criterios:

```text
2.5.5
2.5.6
```

pertenecen al nivel AAA. El proyecto cumple estas decisiones adicionales sin convertir AAA en el nivel general de conformidad.

---

### Tamaño de objetivos interactivos

Todo objetivo interactivo independiente propio de `sitio` utiliza como mínimo:

```text
48px x 48px CSS
```

Este valor supera:

```text
2.5.8 nivel AA
=> 24px x 24px CSS

2.5.5 nivel AAA
=> 44px x 44px CSS
```

La superficie interactiva corresponde al control completo.

Conceptualmente:

```text
Control
=> 48px x 48px CSS como mínimo

Contenido visual interior
=> debe utilizar una dimensión menor
=> no reduce el objetivo
```

Por ejemplo, un icono con:

```text
18px
20px
22px
```

sigue perteneciendo a un control cuyo objetivo mide como mínimo:

```text
48px x 48px CSS
```

La regla se aplica a:

```text
Ítems principales de navegación
Subelementos de navegación
Grupos expandibles
Menú
Selector de idioma
Selector de tema
Botones
Campos de formulario
Acciones explícitas de tarjetas
Accesos a listados completos
Acciones de regreso
Enlaces de medios de contacto
Otros controles independientes propios de sitio
```

Los subelementos de navegación dejan de utilizar:

```text
min-height: 36px
```

y utilizan:

```text
min-height: 48px
```

como el resto de los objetivos independientes.

La aplicación no reduce normalmente un objetivo por debajo de `48px x 48px CSS` utilizando solamente la separación entre objetivos para satisfacer el mínimo AA.

---

### Enlaces integrados dentro del texto

Los enlaces que forman parte de una frase, un párrafo u otro bloque textual conservan su naturaleza de enlace integrado en el texto.

No se transforman en bloques de `48px` de altura únicamente para igualar los controles independientes.

Estos enlaces utilizan la excepción normativa correspondiente a objetivos situados dentro de texto.

Conceptualmente:

```text
Acción independiente
=> objetivo mínimo 48px x 48px CSS

Enlace integrado en texto
=> conservar flujo textual
=> aplicar excepción normativa correspondiente
```

La excepción no se utiliza para acciones visualmente independientes que deben aplicar el mínimo general del proyecto.

---

### Paso del puntero

El estado `hover` funciona exclusivamente como retroalimentación visual adicional.

No constituye una condición necesaria para:

```text
Acceder a una función
Descubrir una acción
Leer información necesaria
Abrir una sección
Cambiar un estado
Navegar
Completar un formulario
```

Conceptualmente:

```text
Sin hover
=> toda la funcionalidad permanece disponible

Con hover
=> retroalimentación visual adicional
```

Los grupos expandibles no se abren ni se cierran solamente al pasar el puntero.

Requieren una activación explícita.

Las acciones de una tarjeta permanecen visibles y disponibles sin depender del paso del puntero.

La existencia de los estados cromáticos `hover` definidos para enlaces y botones no crea una función exclusiva de ese estado.

---

### Contenido adicional al pasar el puntero o recibir foco

La interfaz actual no utiliza contenido necesario que aparezca exclusivamente al pasar el puntero o al recibir foco.

No se incorpora una segunda capa de información cuya consulta dependa de estos estados.

Si posteriormente se introduce contenido adicional activado al pasar el puntero o recibir foco, deberá cumplir simultáneamente:

```text
Descartable
=> debe poder cerrarse sin mover necesariamente el puntero o el foco

Apuntable
=> el puntero debe poder desplazarse hacia el contenido adicional sin provocar su desaparición

Persistente
=> debe permanecer visible mientras continúe la condición correspondiente
   o hasta que el usuario lo descarte
   o hasta que su información deje de ser válida
```

La introducción futura de este tipo de contenido no debe cambiar estas condiciones sin una nueva revisión de accesibilidad.

---

### Activación sencilla

Las funciones propias de `sitio` deben poder realizarse mediante una activación sencilla cuando se utilizan dispositivos de puntero.

Conceptualmente:

```text
Ratón
=> activación sencilla

Tacto
=> toque

Lápiz
=> activación sencilla
```

La aplicación no exige para sus funciones:

```text
Gestos multipunto
Recorridos específicos
Formas dibujadas
Pulsaciones prolongadas
Secuencias gestuales
```

cuando la misma función debe resolverse mediante una activación sencilla.

No se crea una función exclusiva para tacto que carezca de operación equivalente mediante los demás mecanismos disponibles.

---

### Gestos administrados por el navegador

Los gestos normales proporcionados por el navegador permanecen disponibles.

Esto comprende las capacidades normales relacionadas con:

```text
Desplazamiento
Ampliación
Navegación del contenido
Interacción propia del agente de usuario
```

La aplicación no sustituye estas capacidades por gestos propios obligatorios.

Los componentes cuyo contenido necesita desplazamiento horizontal según [Contenido ancho](./21-layout-responsive.md#contenido-ancho) utilizan el comportamiento normal de desplazamiento del navegador.

No se implementa sobre ellos una operación personalizada cuyo único mecanismo sea arrastrar el contenido mediante un recorrido específico.

---

### Cancelación del puntero

Las acciones definitivas no se ejecutan al comenzar la presión del puntero.

La secuencia general utiliza:

```text
Presión inicial
=> no completar acción

Activación cancelada antes de completarse
=> no ejecutar acción

Activación completada
=> ejecutar acción
```

Los controles nativos deben conservar su comportamiento normal de activación.

No se utiliza como mecanismo general:

```text
pointerdown
mousedown
touchstart
```

para completar inmediatamente:

```text
Navegación
Envío
Cambio de tema
Cambio de idioma
Apertura o cierre de grupos
Acciones de tarjetas
```

La acción se produce mediante la activación normal completada del control. Esto permite abandonar una interacción iniciada accidentalmente antes de completarla.

---

### Movimientos de arrastre

Ninguna función propia de `sitio` requiere arrastrar un objeto de un punto hacia otro.

No se utiliza el arrastre como mecanismo único para:

```text
Reordenar contenido
Cambiar un estado
Navegar
Activar un control
Seleccionar una opción
Completar una operación
```

Si en el futuro un componente incorpora una interacción de arrastre, la misma función deberá poder realizarse mediante una operación de puntero sencilla que no requiera el movimiento de arrastre, salvo una excepción normativa aplicable.

Conceptualmente:

```text
Arrastre disponible
=> debe existir como mecanismo adicional

Misma función
=> debe disponer de operación sin arrastre
```

El desplazamiento normal proporcionado por el navegador no se transforma en una función personalizada de arrastre.

---

### Etiqueta visible y nombre accesible

Cuando un control presenta texto visible, su nombre accesible contiene ese texto.

Conceptualmente:

```text
Texto visible
=> incluido en el nombre accesible
```

Si el nombre accesible necesita información adicional:

```text
Nombre accesible
=> conserva el texto visible
=> debe añadir información cuando resulta necesaria
```

No se utiliza un nombre accesible que contradiga o sustituya completamente el texto presentado visualmente.

Los controles formados solamente por iconos siguen utilizando el nombre accesible localizado definido en [Nombres accesibles de controles](#nombres-accesibles-de-controles).

La ausencia de texto visible en un control iconográfico no introduce un texto visual artificial únicamente para este criterio.

---

### Mecanismos de entrada concurrentes

La aplicación no restringe un mecanismo de entrada por detectar o utilizar otro.

Conceptualmente:

```text
Ratón disponible
=> permanece utilizable

Tacto disponible
=> permanece utilizable

Lápiz disponible
=> permanece utilizable

Teclado disponible
=> permanece utilizable
```

Un dispositivo que ofrece simultáneamente varios mecanismos debe conservarlos disponibles.

No se utiliza:

```text
Detección de tacto
=> desactivar ratón

Detección de ratón
=> desactivar tacto

Uso de puntero
=> desactivar teclado
```

La presentación debe ajustar retroalimentaciones visuales que dependen de capacidades reales del dispositivo, pero no debe retirar contenido ni funcionalidad por ese motivo.

---

### Actuación mediante movimiento

`Sitio` no utiliza movimientos físicos del dispositivo o del usuario para activar funciones.

No se utiliza:

```text
Sacudir
Inclinar
Rotar como orden funcional
Movimiento detectado
```

para ejecutar una acción de la aplicación.

El cambio entre orientación vertical y horizontal definido en [Orientación](./21-layout-responsive.md#orientación) no constituye actuación mediante movimiento.

Conceptualmente:

```text
Cambio de orientación
=> cambia el espacio disponible
=> aplica reglas responsive mediante el tamaño de la pantalla
=> no ejecuta una función adicional
```

No existe una función que dependa de sensores de movimiento para su operación normal.

---

## Pruebas de accesibilidad

La validación de accesibilidad combina obligatoriamente pruebas automatizadas y comprobaciones manuales. La comprobación manual no impide el flujo automatizado de la promoción. 

La automatización verifica las condiciones que deben determinarse de forma objetiva mediante el DOM, los estilos calculados, el comportamiento programático y la representación producida por el navegador.

La comprobación manual verifica las condiciones cuya corrección depende además de la percepción, del significado, del orden comprensible de la interacción o del comportamiento real de tecnologías de asistencia. Esta comprobación no impide el flujo automatizado de la promoción. 

Conceptualmente:

```text
Pruebas automatizadas
+ comprobaciones manuales aplicables
=> validación de accesibilidad
```

Una auditoría automática sin violaciones no constituye por sí sola una declaración completa de conformidad WCAG.

### Herramientas

Las pruebas de accesibilidad ejecutadas mediante navegador utilizan:

```text
Playwright
@axe-core/playwright
axe-core
```

`@axe-core/playwright` se integra dentro de las pruebas ya ejecutadas mediante Playwright.

No se incorpora un segundo sistema completo de auditoría mediante:

```text
Lighthouse
Pa11y
```

como requisito de aceptación del proyecto.

Las pruebas unitarias y de componentes siguen utilizando:

```text
Vitest
Herramientas de pruebas de Angular
```

La batería automatizada del proyecto queda formada conceptualmente por:

```text
Vitest
Pruebas de Angular
Playwright
Comprobaciones de accesibilidad mediante axe-core
Comprobaciones automatizadas propias de accesibilidad
```

### Configuración de axe-core

Los análisis correspondientes al nivel general del proyecto utilizan las etiquetas:

```text
wcag2a
wcag2aa
wcag21a
wcag21aa
wcag22aa
```

Conceptualmente:

```typescript
new AxeBuilder({ page })
    .withTags([
        'wcag2a',
        'wcag2aa',
        'wcag21a',
        'wcag21aa',
        'wcag22aa',
    ])
    .analyze();
```

La condición automatizada de aceptación de un análisis es:

```text
violations.length
=> 0
```

Por lo tanto:

```text
0 violaciones
=> comprobación automática aprobada

1 o más violaciones
=> comprobación automática fallida
```

Un resultado que `axe-core` clasifica como no determinable automáticamente no se considera una demostración de conformidad.

Los resultados que necesitan revisión permanecen sujetos a comprobación manual.

Conceptualmente:

```text
Violación
=> fallo automático

Resultado no determinable automáticamente
=> revisión manual

Ausencia de violaciones
=> parte automatizable aprobada
=> no sustituye la revisión manual aplicable
```

### Porcentaje de aceptación

La suite automatizada del proyecto exige:

```text
Pruebas automatizadas aprobadas
-------------------------------- x 100
Pruebas automatizadas ejecutadas

=> 100%
```

La condición obligatoria es:

```text
Aceptación automatizada
=> 100%
```

Por lo tanto:

```text
100% de las pruebas aprobadas
=> validación automatizada aprobada

Resultado menor que 100%
=> validación automatizada fallida
=> no promover hacia main
```

Una prueba automatizada fallida no se compensa mediante otras pruebas aprobadas.

La prueba manual no impide el flujo automatizado de la promoción. 

La misma regla se aplica a las pruebas de accesibilidad.

Conceptualmente:

```text
Pruebas automatizadas de accesibilidad
=> 100% aprobadas

Violaciones detectadas por axe-core
=> 0

Comprobaciones automatizadas propias
=> 100% aprobadas
```

No se utiliza una puntuación estimativa producida por una herramienta como sustitución del porcentaje real de pruebas aprobadas.

Conceptualmente:

```text
Puntuación estimativa de accesibilidad
=> no constituye criterio de aceptación

Porcentaje real de pruebas automatizadas aprobadas
=> debe ser 100%
```

### Alcance por páginas

La auditoría no se limita a Inicio.

Cada tipo conceptual de página debe disponer de cobertura automatizada de accesibilidad.

El alcance incluye:

```text
Inicio
Sobre mí
Contactos
Listado de Certificaciones
Detalle de Certificado
Detalle de Certificación
Listado de Proyectos
Detalle de Proyecto
Listado de Artículos
Detalle de Artículo
Contenido no encontrado
```

No es necesario ejecutar una batería independiente para cada recurso editorial cuando diferentes recursos utilizan exactamente la misma estructura y comportamiento.

La cobertura se establece por:

```text
Tipo de página
Tipo de representación
Estado
Composición
Tema
Contexto lingüístico
Forma de interacción
```

### Estados

Los estados que cambian la estructura, la semántica o el comportamiento deben disponer de cobertura propia.

Esto comprende:

```text
Carga
Contenido disponible
Contenido vacío
Error de carga
Contenido no encontrado

Menú cerrado
Menú abierto
Grupo expandible cerrado
Grupo expandible abierto

Formulario normal
Envío en curso
Validación
Envío satisfactorio
Límite de envíos
Fallo de envío
```

Una página que supera la auditoría en su estado normal no demuestra por sí sola que sus demás estados mantienen la misma accesibilidad.

### Temas

Las comprobaciones cuya respuesta depende de la representación visual deben ejecutarse en Tema claro y Tema oscuro. Esto se aplica especialmente a:

```text
Contraste
Foco visible
Bordes funcionales
Estados semánticos
Enlaces
Botones
Placeholder
Cabecera
```

La igualdad estructural entre temas no permite omitir una comprobación visual cuya combinación cromática cambia.

### Contextos lingüísticos

Las pruebas deben cubrir:

```text
Contenido en el mismo idioma del sistema
Contenido presentado mediante idioma de respaldo
Colección con unidades en idiomas diferentes
Cambio manual de idioma
Navegación interna conservando idioma
Cambio lingüístico interno dentro del contenido
```

La automatización debe comprobar el valor de `lang` correspondiente.

La comprobación manual debe confirmar que el idioma declarado corresponde realmente al contenido presentado y que el cambio lingüístico se aplica a la región semántica adecuada. Esta comprobación no impide el flujo automatizado de la promoción. 

### Datos de prueba

Los datos controlados utilizados por las pruebas deben permitir representar las condiciones necesarias para comprobar:

```text
Cadenas extensas
Contenido con idioma de respaldo
Colecciones multilingües
Alternativas vacías
Alternativas informativas
Imágenes funcionales cuando correspondan
Estados vacíos
Errores
Unidades incompletas
Contenido ancho
Estados del formulario
```

No se utiliza solamente contenido corto y favorable para las pruebas responsive y de accesibilidad.

### Navegación mediante teclado

Playwright debe comprobar automáticamente el comportamiento reproducible mediante teclado.

La cobertura incluye:

```text
Recorrido mediante Tab
Recorrido mediante Shift + Tab cuando corresponde
Activación mediante Enter
Activación mediante Space cuando corresponde al control nativo
Apertura y cierre de grupos
Apertura y cierre del menú estrecho
Activación de enlaces
Activación de botones
Uso del formulario
Cambio de página
```

Las pruebas deben comprobar que:

```text
Contenido oculto
=> no recibe foco

Control visible e interactivo
=> participa en el recorrido correspondiente

Grupo cerrado
=> subelementos fuera del recorrido

Grupo abierto
=> subelementos disponibles

Menú cerrado
=> navegación oculta fuera del recorrido

Menú abierto
=> navegación disponible
```

La comprobación manual debe recorrer también la aplicación utilizando únicamente teclado. Esta comprobación no impide el flujo automatizado de la promoción. 

La revisión manual debe confirmar que el orden resulta lógico y comprensible y que ninguna función queda inaccesible aunque el recorrido programático produzca los elementos esperados. Esta comprobación no impide el flujo automatizado de la promoción. 

### Foco

Las pruebas automatizadas utilizan el elemento activo del documento para comprobar la gestión programática del foco.

Conceptualmente:

```text
document.activeElement
=> elemento esperado
```

La cobertura incluye:

```text
Carga inicial
=> sin movimiento programático

Navegación interna hacia nueva página
=> H1 correspondiente

Actualización dentro de misma página
=> conservar foco

Menú estrecho durante navegación
=> cerrar menú
=> cerrar grupo cuando corresponda
=> foco en H1 del destino

Envío del formulario desde botón
=> conservar foco en botón

Envío mediante teclado desde campo
=> conservar foco en campo
```

También debe comprobarse que el `H1` enfocado programáticamente utiliza:

```text
tabindex="-1"
```

y no forma parte del recorrido secuencial normal.

El estilo calculado del indicador de foco debe corresponder a:

```text
outline-width  => 2px
outline-offset => 2px
```

con el color correspondiente al tema:

```text
Tema claro
=> #141414

Tema oscuro
=> #E2484D
```

La comprobación manual debe confirmar además que el foco:

```text
es claramente perceptible
no queda cubierto por regiones persistentes
no se confunde con otro estado visual
mantiene un recorrido comprensible
```

Esta comprobación no impide el flujo automatizado de la promoción. 

### Estructura semántica

Las pruebas automatizadas deben comprobar la estructura semántica definida para cada página.

Esto incluye:

```text
header
nav
main
H1
Jerarquía de encabezados
Botones nativos
Enlaces nativos
Campos
Etiquetas
Relaciones entre controles y contenido
```

También deben comprobar los estados y relaciones accesibles definidos en esta especificación:

```text
aria-expanded
aria-controls
aria-hidden
aria-busy
aria-invalid
aria-describedby
aria-disabled
readonly
role="status"
role="alert"
tabindex="-1"
```

La presencia de un atributo no constituye por sí sola una prueba suficiente cuando su valor necesita corresponder al estado real del componente.

La prueba debe comprobar la relación entre:

```text
Estado funcional
Estado visual
Estado semántico
```

### Nombres accesibles

La automatización debe comprobar que todo control dispone del nombre accesible correspondiente.

Cuando existe texto visible:

```text
Texto visible
=> debe formar parte del nombre accesible
```

Los controles exclusivamente iconográficos deben disponer de un nombre accesible localizado.

La comprobación manual debe confirmar además que el nombre comunica correctamente la función real del control. Esta comprobación no impide el flujo automatizado de la promoción. 

### Idioma semántico

Las pruebas automatizadas deben comprobar:

```text
lang del documento
Actualización de lang al cambiar idioma
Conservación de lang durante navegación interna
Herencia cuando contenido e interfaz utilizan el mismo idioma
lang propio cuando una variante presentada utiliza otro idioma
lang independiente por unidad en colecciones multilingües
Conservación del idioma de la interfaz alrededor del contenido de respaldo
lang de encabezados pertenecientes a contenido localizado
Contexto lingüístico de alternativas textuales
Cambios lingüísticos internos
Ausencia de lang="" cuando el idioma es conocido
```

Los valores deben corresponder a etiquetas BCP 47 válidas.

La prueba automatizada no intenta determinar el idioma mediante análisis del texto.

La comprobación manual debe comparar la declaración semántica con el idioma realmente presentado. Esta comprobación no impide el flujo automatizado de la promoción. 

### Alternativas textuales

Las pruebas automatizadas deben comprobar que toda imagen de contenido dispone de:

```text
src
alt
```

Debe comprobarse que:

```text
alt
=> existe

alt
=> cadena textual o cadena vacía

alt
=> nunca null
```

La representación debe conservar exactamente el valor recibido desde `sitio-api`.

Los casos de prueba deben incluir:

```text
Proyecto resumido
=> alt=""

Proyecto en detalle
=> alt informativo

Artículo resumido
=> alt=""

Artículo en detalle
=> valor según función editorial

Imagen de artículo
=> valor según función individual

Certificado resumido
=> alt=""

Certificación resumida
=> alt=""

Certificado en detalle
=> alt informativo

Certificación en detalle
=> alt informativo
```

La comprobación manual debe determinar si la alternativa informativa transmite correctamente la función real de la imagen y si una alternativa vacía corresponde efectivamente a una representación redundante o decorativa. Esta comprobación no impide el flujo automatizado de la promoción. 

### Contraste

Las pruebas automatizadas propias deben reproducir el cálculo definido en [Método de cálculo de contraste](#método-de-cálculo-de-contraste).

Los tokens implementados deben comprobarse frente a todas las superficies permitidas para su función.

Los umbrales utilizados son:

```text
Texto normal AA
=> >= 4.5:1

Texto grande AA
=> >= 3:1

Texto normal AAA
=> >= 7:1

Texto grande AAA
=> >= 4.5:1

Información no textual necesaria
=> >= 3:1
```

Las pruebas deben utilizar el valor completo del contraste.

No deben redondear un valor inferior hasta convertirlo en conforme.

Las combinaciones del tema claro deben conservar como mínimo los resultados registrados en [Auditoría de contraste del tema claro](#auditoría-de-contraste-del-tema-claro).

Las combinaciones del tema oscuro deben conservar como mínimo los resultados registrados en [Auditoría de contraste del tema oscuro](#auditoría-de-contraste-del-tema-oscuro).

Un cambio de un token que haga fallar una combinación permitida debe producir una prueba fallida.

La auditoría mediante `axe-core` complementa estas pruebas, pero no sustituye la comprobación matemática de los tokens.

### Cabecera y fondos variables

La prueba automática debe conservar la condición:

```text
Capa negra mínima
=> 60%

Texto
=> #F2F1EE

Peor fondo efectivo
=> #666666

Contraste mínimo calculado
=> 5.0834876786:1
```

La comprobación manual debe confirmar que la capa de al menos `60%` cubre realmente toda la región ocupada por:

```text
Nombre
Descripción breve
```

en cada composición donde esos textos aparecen sobre la fotografía.

También debe verificarse que el crecimiento del bloque textual por redimensionamiento o espaciado amplía la región protegida.

Esta comprobación manual no impide el flujo automatizado de la promoción. 

### Uso del color

La automatización debe comprobar la presencia de texto, semántica o señal visual adicional en los estados cuyo significado no debe depender exclusivamente del color.

La comprobación manual debe confirmar que:

```text
Éxito
Advertencia
Error
Información
Estados interactivos
Enlaces dentro de texto
```

siguen siendo comprensibles cuando la distinción cromática no se utiliza como única fuente de información.

### Redimensionamiento del texto

La prueba automatizada debe representar el texto con:

```text
200%
```

del tamaño de referencia y comprobar que:

```text
Contenido
=> permanece presente

Controles
=> permanecen presentes

Acciones
=> permanecen disponibles

Texto necesario
=> no queda recortado ni truncado

Contenedores
=> crecen o se reorganizan
```

La prueba debe incluir todos los niveles de la escala tipográfica definidos en [Escala tipográfica](./16-tipografia-y-espaciado.md#escala-tipográfica).

La comprobación manual debe confirmar visualmente la ausencia de:

```text
Recorte
Superposición
Ocultación
Truncamiento
Pérdida de legibilidad
```

Esta comprobación manual no impide el flujo automatizado de la promoción. 

### Reflujo

Playwright debe ejecutar la composición con:

```text
ancho => 320px CSS
```

Para el contenido normal debe cumplirse:

```text
document.documentElement.scrollWidth
<=
document.documentElement.clientWidth
```

Los componentes que utilizan legítimamente desplazamiento horizontal propio no deben ampliar el ancho horizontal de la página completa.

La prueba debe comprobar además que:

```text
Contenido
Controles
Navegación
Estados
Acciones
```

permanecen disponibles.

La comprobación manual debe incluir también el caso equivalente mediante zoom real del navegador:

```text
1280px CSS
+ zoom del 400%
=> 320px CSS disponibles
```

La prueba manual debe confirmar que la reorganización continúa siendo utilizable y que los componentes con desplazamiento propio se encuentran limitados a su región. Esta comprobación no impide el flujo automatizado de la promoción. 

### Espaciado del texto

Las pruebas automatizadas deben aplicar simultáneamente:

```text
line-height
=> 1.5 veces el tamaño de fuente

espacio posterior a párrafos
=> 2 veces el tamaño de fuente

letter-spacing
=> 0.12 veces el tamaño de fuente

word-spacing
=> 0.16 veces el tamaño de fuente
```

Con estos valores activos debe conservarse:

```text
Contenido
Funcionalidad
Controles
Etiquetas
Mensajes
Acciones
```

La comprobación manual debe confirmar que la representación resultante continúa siendo legible y que no existe superposición ni pérdida visual. Esta comprobación no impide el flujo automatizado de la promoción. 

### Orientación

Las pruebas automatizadas deben utilizar composiciones equivalentes con dimensiones intercambiadas para verificar:

```text
Orientación vertical
Orientación horizontal
```

El cambio debe conservar el mismo contenido y las mismas funciones y debe seleccionar la composición responsive correspondiente a las dimensiones resultantes.

La comprobación manual mediante un dispositivo que permita cambio real de orientación debe confirmar el mismo comportamiento. Esta comprobación no impide el flujo automatizado de la promoción. 

### Objetivos interactivos

Los objetivos interactivos independientes propios de `sitio` se miden sobre la geometría final producida por el navegador.

La comprobación utiliza:

```text
getBoundingClientRect()
```

y exige:

```text
width  >= 48px
height >= 48px
```

para los objetivos independientes a los que se aplica la regla general.

La medición corresponde al elemento que recibe realmente la interacción.

No se mide solamente:

```text
SVG
Icono
Texto interior
```

cuando estos elementos pertenecen a un control mayor.

Los enlaces integrados dentro del texto quedan fuera de esta exigencia de `48px x 48px CSS` según la excepción ya definida.

La comprobación manual debe confirmar que el área percibida e interactiva coincide realmente con el control que la interfaz presenta. Esta comprobación no impide el flujo automatizado de la promoción. 

### Puntero, tacto y teclado

Las funciones deben comprobarse mediante:

```text
Ratón
Tacto emulado
Teclado
```

cuando la automatización de Playwright permite reproducir la interacción correspondiente.

Las mismas acciones deben producir el mismo resultado funcional.

Debe comprobarse especialmente:

```text
Navegación
Grupos expandibles
Menú
Cambio de idioma
Cambio de tema
Acciones de tarjetas
Formulario
```

La existencia de un contexto táctil no debe retirar la funcionalidad disponible mediante los demás mecanismos.

La comprobación manual debe confirmar además el uso mediante tacto real cuando se disponga del dispositivo correspondiente. Esta comprobación no impide el flujo automatizado de la promoción. 

### Dependencia de hover

Las pruebas deben comprobar que las funciones necesarias siguen disponibles en un contexto sin `hover`.

Conceptualmente:

```text
hover ausente
=> contenido necesario disponible
=> funciones disponibles
=> controles disponibles
=> estados alcanzables mediante activación
```

Los grupos expandibles deben conservar la activación explícita.

Las acciones de las tarjetas deben permanecer visibles y utilizables.

### Cancelación del puntero

Cuando una interacción de puntero se inicia y se cancela antes de completar la activación normal:

```text
Acción
=> no ejecutada
```

Las pruebas deben comprobar que las acciones definitivas no ocurren solamente por:

```text
pointerdown
mousedown
touchstart
```

Los controles nativos deben mantener su semántica normal de activación.

La comprobación manual debe confirmar que una interacción iniciada accidentalmente puede abandonarse antes de completar la acción. Esta comprobación no impide el flujo automatizado de la promoción. 

### Arrastre

Las pruebas deben comprobar que ninguna función propia del sitio exige un arrastre como único mecanismo.

Cuando exista una representación visual que admita arrastre en el futuro, deberá existir también una operación sencilla equivalente sin arrastre.

El desplazamiento normal de contenido administrado por el navegador no se considera una operación de arrastre funcional propia de `sitio`.

### Formulario

Las pruebas automatizadas deben comprobar todos los estados semánticos del formulario.

Durante el envío:

```text
form
=> aria-busy="true"

Campos textuales
=> readonly

Campos
=> no disabled

Botón
=> aria-disabled="true"

Botón
=> no disabled

Texto del botón
=> enviando...

role="status"
=> fuera del formulario ocupado

Foco
=> permanece en el control de origen
```

Una nueva activación durante la operación no debe iniciar una segunda solicitud.

Al finalizar:

```text
aria-busy
=> deja de indicar operación pendiente

readonly
=> retirado

aria-disabled
=> retirado

Botón
=> Enviar

Región de progreso
=> deja de anunciar enviando...
```

Después se comprueba el resultado correspondiente:

```text
Éxito
=> role="status"

Límite
=> role="status"

Fallo
=> role="alert"

Validación de campo
=> aria-invalid
=> aria-describedby
```

La comprobación manual mediante tecnología de asistencia debe confirmar que progreso, éxito, límite, validación y fallo se comunican de acuerdo con su significado. Esta comprobación no impide el flujo automatizado de la promoción. 

### Estados de carga

Las pruebas automatizadas deben comprobar:

```text
Unidad pendiente
=> aria-busy="true"

Skeleton
=> aria-hidden="true"

Skeleton
=> sin foco

Skeleton
=> sin controles ficticios

Finalización
=> retirar estado pendiente
=> representar contenido, vacío o error correspondiente
```

Las unidades independientes deben mantener estados independientes.

La prueba no debe considerar toda la página ocupada solamente porque una unidad continúa pendiente.

### Cambio de página

Las pruebas automatizadas deben comprobar conjuntamente:

```text
<title>
H1
Foco
Menú
Grupo expandible
```

Durante una navegación interna hacia una nueva página:

```text
Actualizar <title>
Representar H1
Cerrar Menú cuando corresponda
Cerrar grupo cuando corresponda
Mover foco al H1
```

El `H1` debe utilizar:

```text
tabindex="-1"
```

sin incorporarse al recorrido normal mediante `Tab`.

La carga inicial no debe mover programáticamente el foco.

Una actualización dentro de la misma página tampoco debe moverlo al `H1`.

La comprobación manual mediante tecnología de asistencia debe confirmar que el título del documento y el encabezado principal enfocado proporcionan contexto suficiente sin una región adicional de anuncio de ruta. Esta comprobación no impide el flujo automatizado de la promoción. 

### Tecnologías de asistencia

La prueba real mediante lector de pantalla es obligatoriamente manual.

La automatización debe comprobar la semántica que utilizará la tecnología de asistencia, pero no debe inferir a partir del DOM que el anuncio real ya fue validado.

La comprobación manual debe cubrir como mínimo:

```text
Regiones
Jerarquía de encabezados
Navegación
Nombres de controles
Grupos expandibles
Idioma del documento
Cambios de idioma
Alternativas textuales
Formulario
Validaciones
Envío en curso
Confirmación
Límite de envíos
Errores
Estados de carga
Cambio de página
```

### Capturas y comparación visual

Las capturas no deben utilizarse como apoyo para revisar una representación concreta, las pruebas son hechas mediante:

```text
Pruebas funcionales
Comprobaciones semánticas
Cálculos de contraste
Revisión mediante teclado
Revisión mediante tecnologías de asistencia
Comprobación manual
```

### Integración y promoción

Las pruebas automatizadas de accesibilidad forman parte de la validación obligatoria anterior a la promoción hacia `main`.

Conceptualmente:

```text
Rama de trabajo
        |
        V
dev
        |
        V
Suite automatizada
        |
        +-- pruebas unitarias
        +-- pruebas de componentes
        +-- pruebas mediante navegador
        +-- auditoría automatizada de accesibilidad
        +-- comprobaciones automatizadas propias
        |
        V
100% aprobadas
        |
        V
Comprobaciones manuales aplicables
        |
        V
main
```

Una violación de `axe-core` o cualquier otra prueba automatizada fallida impide la promoción.

Las comprobaciones manuales aplicables deben completarse antes de promover cambios que modifiquen:

```text
Estructura semántica
Navegación
Foco
Interacción
Estados
Formulario
Representación visual accesible
Contraste
Tipografía
Responsive
Reflujo
Objetivos interactivos
Idioma semántico
Alternativas textuales
Contenido cuya accesibilidad depende de una decisión editorial
```

Un resultado automatizado correcto no exime la comprobación manual cuando el aspecto cambiado pertenece a una condición que necesita evaluación humana.

---

## Resumen de accesibilidad

```text
Referencia                    => WCAG 2.2
Nivel                          => AA
Orden visual                   => orden del DOM => orden de foco
Foco tema claro                => 2px / offset 2px / #141414
Foco tema oscuro               => 2px / offset 2px / #E2484D
Skeleton visual                => fuera del contenido accesible
Unidad cargando                => aria-busy
Grupo expandible               => aria-expanded
Campo inválido                 => aria-invalid
Error asociado                 => aria-describedby
Formulario enviando            => aria-busy="true"
Campos durante envío           => readonly
Campos durante envío           => no utilizar disabled
Botón durante envío            => aria-disabled="true"
Botón durante envío            => no utilizar disabled
Texto del botón                => enviando...
Segundo envío simultáneo       => bloqueado funcionalmente
Progreso del envío             => role="status"
Región de progreso             => fuera del formulario aria-busy
Foco durante envío             => conservar en el control de origen
Resultado no urgente           => role="status"
Fallo de envío                 => role="alert"
Carga inicial                  => sin movimiento programático de foco
Cambio interno de página        => foco en H1
H1 de una nueva página          => tabindex="-1"
main                           => no recibe foco por el cambio de página
Cambio dentro de misma página   => conservar foco
Anuncio adicional de ruta      => no utilizar aria-live
Imagen de contenido            => src y alt obligatorios
alt                            => texto o cadena vacía
alt                            => no utilizar null
Alternativa de contenido       => determinada por sitio-api
Representación de alt          => utilizar exactamente el valor recibido
Proyecto resumido              => alt=""
Proyecto en detalle            => alt informativo
Artículo resumido              => alt=""
Artículo en detalle            => alt según función editorial
Imagen de artículo Markdown    => alt según función individual
Certificado resumido           => alt=""
Certificación resumida         => alt=""
Certificado en detalle         => alt informativo
Certificación en detalle       => alt informativo
Contactos                      => iconos, sin imagen de contenido
Idioma principal               => lang del documento
Idioma principal WCAG          => 3.1.1 nivel A
Idioma de las partes WCAG      => 3.1.2 nivel AA
Etiqueta lingüística           => BCP 47
Idioma del documento           => idioma activo del sistema
Cambio manual de idioma        => actualizar lang del documento
Navegación con mismo idioma    => conservar lang del documento
Contenido en mismo idioma      => heredar lang
Contenido mediante respaldo    => declarar lang de la variante
Documento durante respaldo     => conservar idioma activo del sistema
Colección multilingüe          => lang independiente por unidad
Texto de interfaz              => idioma activo del sistema
H1 de contenido de respaldo    => idioma real de la variante
Alt de contenido localizado    => idioma de la variante
Cambio interno de idioma       => lang en la parte correspondiente
Contenido Markdown             => conservar cambios lingüísticos editoriales
Detección automática de idioma => no utilizar
lang redundante                => no repetir cuando se hereda correctamente
lang vacío con idioma conocido => no utilizar
AAA específico para lang       => no existe requisito adicional
Orientación WCAG               => 1.3.4 nivel AA
Redimensionamiento WCAG        => 1.4.4 nivel AA
Reflujo WCAG                   => 1.4.10 nivel AA
Espaciado del texto WCAG       => 1.4.12 nivel AA
Presentación visual            => 1.4.8 nivel AAA relacionado
Texto hasta 200%               => conservar contenido y funcionalidad
Zoom                           => no restringir
Reflujo                        => 320px CSS
Página durante reflujo         => sin desplazamiento horizontal normal
Contenido bidimensional        => desplazamiento horizontal propio cuando sea necesario
Espaciado cambiado             => conservar contenido y funcionalidad
Orientación vertical           => funcionamiento completo
Orientación horizontal         => funcionamiento completo
Contenido en hover o foco WCAG => 1.4.13 nivel AA
Gestos del puntero WCAG        => 2.5.1 nivel A
Cancelación del puntero WCAG   => 2.5.2 nivel A
Etiqueta en el nombre WCAG     => 2.5.3 nivel A
Actuación por movimiento WCAG  => 2.5.4 nivel A
Tamaño mejorado WCAG           => 2.5.5 nivel AAA
Entrada concurrente WCAG       => 2.5.6 nivel AAA
Arrastre WCAG                  => 2.5.7 nivel AA
Tamaño mínimo WCAG             => 2.5.8 nivel AA
Objetivo propio independiente  => mínimo 48px x 48px CSS
Objetivo AA WCAG               => mínimo normativo 24px x 24px CSS
Objetivo AAA WCAG              => mínimo normativo 44px x 44px CSS
Enlace integrado en texto      => excepción normativa correspondiente
hover                          => retroalimentación visual adicional
Función dependiente de hover   => no utilizar
Apertura de grupos por hover   => no utilizar
Gestos multipunto obligatorios => no utilizar
Recorridos obligatorios        => no utilizar
Arrastre obligatorio           => no utilizar
Acción definitiva al presionar => no utilizar
Activación completada          => ejecutar acción
Nombre accesible con texto     => contiene el texto visible
Ratón                          => conservar disponible
Tacto                          => conservar disponible
Lápiz                          => conservar disponible
Teclado                        => conservar disponible
Movimiento físico              => no utilizar para activar funciones
Gestos normales del navegador  => conservar
Pruebas de navegador           => Playwright
Auditoría automática           => @axe-core/playwright
Motor de auditoría             => axe-core
Etiquetas de auditoría         => wcag2a, wcag2aa, wcag21a, wcag21aa, wcag22aa
Violaciones automáticas        => 0
Aceptación automatizada        => 100%
Resultado no determinable      => revisión manual
Pruebas de teclado             => automáticas y manuales
Pruebas de foco                => automáticas y manuales
Pruebas de lector de pantalla  => manuales
Contraste                      => cálculo automático + comprobación manual cuando corresponda
Texto de prueba                => hasta 200%
Reflujo de prueba              => 320px CSS
Zoom manual equivalente        => 400% sobre 1280px CSS
Objetivo medido                => mínimo 48px x 48px CSS
Espaciado de prueba            => 1.5 / 2 / 0.12 / 0.16
Captura píxel a píxel          => no constituye criterio de conformidad
```

---

