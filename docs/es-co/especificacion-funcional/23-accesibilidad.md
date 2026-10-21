# 23. Accesibilidad

La accesibilidad forma parte de la estructura, la presentación y el comportamiento de la aplicación.

El proyecto utiliza el nivel AA de las pautas WCAG de W3C/WAI como referencia de conformidad.

Cuando una decisión alcanza también requisitos de niveles superiores, debe conservarse sin convertir ese nivel adicional en una exigencia general para toda la aplicación.

La accesibilidad no se resuelve mediante una representación paralela de la interfaz.

La misma estructura utilizada visualmente debe proporcionar la información, jerarquía, relaciones y estados necesarios para diferentes formas de interacción.

## Orden y navegación mediante teclado

El orden visual, el orden estructural del documento y el recorrido normal mediante teclado deben permanecer coherentes.

La presentación no debe reorganizar visualmente elementos de forma que contradiga el orden semántico utilizado para la navegación.

La aplicación prioriza la estructura natural del documento y los controles nativos antes que mecanismos manuales para cambiar el orden de foco.

Todos los controles interactivos deben utilizarse mediante teclado cuando su naturaleza permita interacción.

El foco debe permanecer visible durante la navegación.

Los elementos que forman visualmente parte de un mismo control no deben introducir objetivos de foco independientes cuando no representan acciones distintas.

Conceptualmente:

```text
Orden visual
=> orden estructural
=> orden de navegación
```

La navegación mediante teclado debe permitir recorrer la interfaz sin producir saltos arbitrarios ni secuencias distintas de la estructura presentada visualmente.

## Estructura semántica

La estructura global utiliza regiones semánticas correspondientes a la cabecera, navegación y contenido principal.

Estas regiones permiten identificar la organización general del documento sin convertirse automáticamente en elementos de foco.

La jerarquía de encabezados representa la estructura real del contenido.

Conceptualmente:

```text
Página
=> encabezado principal

Sección principal
=> encabezado de sección

Subsección
=> nivel subordinado correspondiente
```

El nivel de un encabezado se determina por su posición semántica y no por el tamaño visual deseado.

La carga inicial de una página no desplaza automáticamente el foco hacia una región únicamente por su existencia.

La composición definida no incorpora un control adicional específico para saltar al contenido principal.

La identificación y navegación entre las regiones repetidas se apoya en la estructura semántica, la jerarquía de encabezados y la organización de la navegación.

## Controles expandibles

Los grupos expandibles comunican su estado de forma visual y semántica.

La fila que identifica el grupo constituye un único control.

El indicador gráfico de apertura o cierre forma parte de ese control y no representa una acción independiente.

La superficie interactiva corresponde al control completo y no solamente al icono o al texto que contiene.

Conceptualmente:

```text
Grupo cerrado
=> estado visual cerrado
=> estado semántico cerrado

Grupo abierto
=> estado visual abierto
=> estado semántico abierto
```

Los elementos pertenecientes a una región cerrada no forman parte del recorrido mediante teclado mientras permanecen ocultos.

Cuando la región vuelve a abrirse, sus elementos recuperan su participación normal en la navegación.

La misma regla se aplica al menú de las composiciones estrechas.

Los indicadores visuales deben quedar excluidos de las tecnologías de asistencia cuando la información equivalente ya está expresada semánticamente por el propio control.

## Nombres de controles

Todo control interactivo debe disponer de un nombre accesible que comunique su función.

Cuando el propio control contiene texto visible suficiente, ese texto constituye su identificación principal.

Cuando existe un nombre accesible definido adicionalmente para un control con texto visible, debe contener ese mismo texto visible y no sustituirlo por una identificación diferente.

Un icono que acompaña un texto con el mismo significado no necesita anunciarse de forma independiente.

Cuando un control utiliza solamente un icono, debe proporcionar un nombre localizado que describa la acción disponible.

Conceptualmente:

```text
Control con texto suficiente
=> texto visible identifica la acción
=> nombre accesible conserva ese texto

Control solamente con icono
=> nombre accesible localizado
```

El nombre debe describir la función del control y no limitarse a describir la forma del icono.

## Interacción por puntero y tacto

Los controles interactivos independientes deben disponer de un área de interacción suficiente para su utilización mediante puntero y tacto.

El objetivo interactivo corresponde al control completo.

El tamaño visual de un icono, texto u otro contenido interior no determina por sí mismo el tamaño del objetivo.

Conceptualmente:

```text
Control
=> objetivo interactivo completo

Icono o texto interior
=> contenido del control
=> no objetivo independiente
```

La navegación, los grupos expandibles, los selectores, los botones, los campos, las acciones explícitas de las tarjetas y los demás controles independientes aplican esta misma regla.

Los subelementos de navegación utilizan el mismo tamaño mínimo general de interacción definido para los demás controles independientes.

Los enlaces integrados dentro de párrafos u otros bloques de texto conservan su naturaleza textual.

No se convierten artificialmente en controles de mayor tamaño únicamente para igualar la geometría de los objetivos independientes.

La misma funcionalidad debe permanecer disponible mediante los mecanismos de entrada compatibles con el dispositivo.

Conceptualmente:

```text
Ratón
Tacto
Lápiz
Teclado
=> mismos controles
=> mismas funciones
```

La disponibilidad de un mecanismo de entrada no debe provocar la desactivación de otro mecanismo también disponible.

La interfaz no mantiene versiones funcionales diferentes para dispositivos de puntero distintos.

El paso del puntero sobre un elemento debe utilizarse solamente como retroalimentación visual adicional.

Ningún contenido, estado, destino ni función necesarios deben depender exclusivamente de que el puntero permanezca sobre un elemento.

Conceptualmente:

```text
Pasar el puntero
=> refuerzo visual

Activación
=> acceso a la función
```

Los grupos de navegación deben continuar abriéndose mediante una activación explícita.

No deben abrirse únicamente como consecuencia de pasar el puntero.

La aplicación no utiliza contenido necesario que aparezca exclusivamente al pasar el puntero o al recibir foco.

Cuando una interfaz incorpore contenido adicional asociado a estos estados, ese contenido debe permitir ser descartado cuando corresponda, debe permanecer accesible al desplazar el puntero hacia él y debe continuar visible mientras persista la condición que justifica su presencia.

Las funciones propias de la aplicación deben utilizar una activación sencilla.

No deben depender de:

```text
Gestos con múltiples puntos
Recorridos específicos del puntero
Pulsaciones prolongadas
Combinaciones gestuales
```

cuando una activación sencilla debe realizar la misma función.

La aplicación no utiliza el arrastre como requisito para realizar una función.

Si un componente incorpora una interacción visual mediante arrastre, la misma operación debe disponer también de una forma equivalente que no requiera arrastrar.

El desplazamiento normal de la página y de los componentes cuyo contenido necesita desplazamiento propio continúa perteneciendo al comportamiento de navegación y no constituye una operación de arrastre de un elemento de interfaz.

Las acciones mediante puntero deben completarse con la activación normal del control.

La presión inicial no debe ejecutar por sí sola una acción definitiva.

Conceptualmente:

```text
Iniciar presión
=> no completar acción

Cancelar antes de completar
=> no ejecutar

Completar activación
=> ejecutar acción
```

Esta regla se aplica a navegación, controles globales, grupos expandibles, acciones de tarjetas, enlaces y controles del formulario.

Los controles deben utilizar su comportamiento normal de activación para permitir cancelar una interacción iniciada accidentalmente antes de completarla.

La aplicación no utiliza movimientos físicos del dispositivo o del usuario para activar funciones.

Los cambios de orientación no constituyen una acción funcional.

Solamente cambian el espacio disponible y aplican las reglas responsive correspondientes.

Los gestos normales administrados por el navegador para desplazamiento, ampliación u otras funciones propias del agente de usuario no deben bloquearse ni sustituirse por gestos personalizados de la aplicación.

## Formulario

Todos los campos visibles del formulario disponen de una etiqueta visible y asociada estructuralmente al control correspondiente.

La etiqueta constituye la identificación principal del campo.

Los textos auxiliares dentro de un control deben proporcionar una instrucción breve, pero no sustituyen la etiqueta ni contienen por sí solos información indispensable para completar correctamente el campo.

Las instrucciones utilizadas antes de la entrada deben permanecer generales y coherentes con la función del campo.

Los errores de validación aparecen junto al campo correspondiente y se relacionan semánticamente con ese control.

El campo afectado comunica también su estado inválido.

El mensaje debe permitir identificar qué necesita corregirse sin depender solamente de un cambio cromático.

Los valores introducidos se conservan durante la validación.

La aparición de errores de campo no provoca una sucesión automática de cambios de foco.

Los errores individuales tampoco se convierten todos simultáneamente en avisos interruptivos.

Conceptualmente:

```text
Campo
=> etiqueta visible
=> instrucción auxiliar cuando corresponde
=> estado de validación
=> mensaje relacionado cuando existe un error
```

## Envío en curso del formulario

El estado de envío en curso debe comunicarse de forma visual, funcional y semántica.

El formulario como conjunto comunica que existe una operación pendiente.

Los campos conservan los valores introducidos y pasan temporalmente a un estado no cambiable.

Este estado no los retira del recorrido normal de foco ni impide que su contenido continúe disponible para las tecnologías de asistencia.

Conceptualmente:

```text
Campo durante el envío
=> conserva su valor
=> no permite cambio
=> permanece disponible para el foco
```

El control de envío permanece presente y conserva su posición en el recorrido mediante teclado.

Durante la operación comunica que temporalmente no debe iniciar otra solicitud.

El cambio visible de:

```text
enviar
=> enviando...
```

también comunica el estado actual del control.

La indisponibilidad temporal del control debe corresponder a un bloqueo funcional real de cualquier nueva tentativa de envío por el backend y por los campos visuales y botones del formulario mientras la solicitud anterior continúa pendiente.

No basta con representar visualmente que el control está indisponible.

Conceptualmente:

```text
Operación pendiente
=> control temporalmente no disponible
=> nueva activación no inicia otra solicitud
```

El backend debe bloquear otras solicitudes para el mismo host mientras una esté en transito.

El estado de progreso se comunica además mediante un anuncio no interruptivo.

La comunicación debe producirse sin desplazar el foco.

No se utiliza un aviso interruptivo para indicar que el envío está en curso.

No se añade una segunda representación visual de `enviando...` cuando el propio control ya proporciona ese texto.

La información destinada a comunicar el progreso a tecnologías de asistencia se mantiene separada de la región que está siendo procesada.

Esto permite que el estado de progreso pueda comunicarse inmediatamente aunque el formulario completo se encuentre marcado como ocupado por la operación.

Conceptualmente:

```text
Formulario
=> operación en curso

Control
=> enviando...

Comunicación accesible
=> operación en curso
=> no interruptiva
=> sin mover foco
```

El inicio del envío conserva el foco en el elemento desde el que se realizó la acción.

Si la acción se inicia desde el control de envío:

```text
Control de envío
=> conserva foco
```

Si la acción se inicia mediante teclado desde otro control del formulario:

```text
Control de origen
=> conserva foco
```

No se mueve el foco hacia el mensaje de progreso.

Cuando la operación termina, los estados temporales se restauran antes de representar el resultado final.

Conceptualmente:

```text
Formulario
=> deja de comunicar operación pendiente

Campos
=> vuelven a permitir cambio

Control
=> vuelve a estar disponible
=> vuelve a presentar Enviar

Comunicación de progreso
=> deja de estar activa
```

Después se utiliza la comunicación correspondiente al resultado ya definido para éxito, límite de envíos, validación o fallo.

No se anuncia adicionalmente que la operación terminó cuando el propio resultado ya proporciona esa información.

## Mensajes del formulario

Los resultados generales del formulario permanecen visibles mientras continúan siendo pertinentes.

No crean avisos que desaparecen automáticamente después de un período breve, sus avisos son fijos.

El estado de envío en curso se comunica mediante un anuncio no interruptivo mientras la operación permanece pendiente.

Una confirmación satisfactoria se comunica mediante un anuncio no interruptivo.

La información relacionada con un límite temporal de envío también utiliza una comunicación no interruptiva.

Un fallo que impide completar el envío utiliza una comunicación inmediata adecuada a un error de operación.

Estos avisos no desplazan automáticamente el foco.

Los mensajes de cada campo permanecen separados de los avisos generales del formulario.

El color semántico depende del significado de un resultado.

## Estados de carga

Los skeletons no constituyen contenido accesible.

La información semántica de carga pertenece a la unidad real cuyo contenido todavía se encuentra pendiente.

Conceptualmente:

```text
Unidad pendiente
=> comunica estado de carga

Skeleton
=> representación visual
=> no constituye contenido independiente
```

Las unidades independientes mantienen estados independientes.

La carga de una tarjeta, sección o elemento concreto no convierte automáticamente toda la página en una única región pendiente.

Los skeletons no reciben foco ni contienen controles ficticios.

No se incorpora un mensaje oculto de carga únicamente para crear una segunda representación destinada a tecnologías de asistencia.

Cuando la operación termina, la unidad deja de comunicar el estado pendiente y adopta el estado final correspondiente.

## Movimiento de los skeletons

La indicación visual de carga debe utilizar movimiento hasta el contenido cargarse por completo o un error ocurra.

Conceptualmente:

```text
Movimiento de franja de luminosidad en gradiente 
=> skeleton con indicación animada
```

El usuario no controla este movimiento porque forma parte de la estructura del sitio para informar que el contenido todavía no está disponible.

## Imágenes

Las alternativas textuales se determinan según la función que cada imagen cumple dentro de su contexto.

Una misma forma visual debe necesitar tratamientos diferentes cuando cambia su función.

La aplicación distingue conceptualmente entre:

```text
Imagen decorativa
Imagen informativa
Imagen funcional
Imagen de texto necesaria
Imagen compleja
Imagen relacionada con una experiencia sensorial específica
```

Una imagen puramente decorativa no debe introducir información redundante para tecnologías de asistencia.

Cuando resulta adecuado, la decoración se incorpora mediante recursos de presentación.

Si una imagen decorativa necesita existir como elemento de imagen, utiliza una alternativa vacía.

Una imagen informativa dispone de una alternativa que transmite la información esencial que aporta en ese contexto.

Una imagen funcional comunica mediante su alternativa la función o el destino correspondiente.

Una imagen que necesariamente presenta texto debe proporcionar una alternativa equivalente al contenido relevante.

Una imagen compleja debe utilizar una identificación breve acompañada por una descripción adicional cuando la información no debe expresarse adecuadamente mediante una alternativa corta.

Una imagen cuya finalidad incluye una experiencia sensorial concreta utiliza una identificación descriptiva compatible con esa función.

Una imagen que transmite información necesaria no se transforma en un recurso puramente decorativo para evitar proporcionar una alternativa textual.

Las imágenes que forman parte del contenido proporcionado por `sitio-api` incluyen siempre su fuente y su alternativa textual.

La alternativa textual constituye parte del contenido y es determinada por `sitio-api` de acuerdo con la función de la imagen en la representación solicitada.

La alternativa puede permanecer vacía cuando la imagen no debe aportar información adicional a las tecnologías de asistencia, pero no se omite ni utiliza un valor nulo.

`Sitio` utiliza directamente la alternativa recibida.

No genera una alternativa a partir de otros campos, no sustituye el valor recibido, no decide vaciarlo y no reclasifica por su cuenta la función de la imagen.

Conceptualmente:

```text
sitio-api
=> determina la alternativa según la función de la imagen y el contexto solicitado

sitio
=> representa la alternativa recibida sin reinterpretarla
```

Esta separación permite que una misma imagen de contenido pueda recibir un tratamiento accesible distinto cuando aparece en representaciones diferentes.

En `Sobre mí`, las imágenes acompañan al contenido del bloque y su alternativa es definida editorialmente según la función que desempeñan.

Cuando la propia imagen constituye la representación de una acción, la alternativa proporcionada debe comunicar la función o el destino correspondiente.

En las representaciones resumidas de proyectos, la imagen funciona como apoyo visual de información que ya identifica el recurso y utiliza una alternativa vacía.

En el detalle de un proyecto, la imagen principal es informativa y dispone de una alternativa que comunica la información visual relevante.

En las representaciones resumidas de artículos, la imagen principal funciona como apoyo editorial y utiliza una alternativa vacía.

En el detalle de un artículo, la imagen principal puede continuar siendo una representación editorial sin información adicional o puede aportar información propia.

La alternativa proporcionada corresponde a esa función editorial.

Las imágenes incluidas dentro del contenido de los artículos se consideran individualmente.

Cada imagen recibe la alternativa correspondiente a su propia función dentro del contenido.

En las representaciones resumidas de certificados y certificaciones, la imagen funciona como apoyo visual de información ya disponible en la tarjeta y utiliza una alternativa vacía.

En el detalle de un certificado o una certificación, la imagen del documento constituye información y dispone de una alternativa breve que identifica aquello que se representa.

La alternativa no necesita reproducir todos los datos del documento cuando esos datos ya forman parte del contenido estructurado de la página.

La información extensa necesaria para comprender un documento debe formar parte del contenido accesible de la página y no concentrarse únicamente en una alternativa textual.

Las tarjetas de Contactos utilizan iconos y no imágenes de contenido para representar los medios disponibles.

## Iconos

Los iconos utilizados como apoyo de un texto visible suficiente no se anuncian de forma independiente.

Conceptualmente:

```text
Icono + texto suficiente
=> texto comunica el significado
=> icono funciona como apoyo visual
```

Cuando un icono constituye por sí mismo un control, el control dispone de un nombre accesible localizado.

Cuando un icono representa visualmente un estado que también está disponible semánticamente, debe quedar fuera de la información anunciada de forma independiente.

La existencia de una representación semántica no elimina la necesidad de que el estado continúe siendo perceptible visualmente.

## Fotografía de la cabecera

La fotografía personal de la cabecera constituye información relacionada con la identidad presentada por el sitio.

No se considera una imagen puramente decorativa.

La fotografía dispone de una alternativa textual localizada que identifica su función como retrato de la persona presentada.

La representación lingüística del nombre utilizada en esa alternativa corresponde al idioma del contenido.

La alternativa completa se localiza de acuerdo con la estructura natural de cada idioma y no depende de concatenaciones parciales que presupongan una misma construcción lingüística.

La función informativa de la fotografía permanece igual en las distintas composiciones y estados de la cabecera.

El fondo visual que acompaña a la fotografía debe permanecer como elemento puramente decorativo cuando no aporta información adicional.

## Localización de la accesibilidad

Los textos utilizados para proporcionar accesibilidad forman parte de la misma internacionalización del sitio.

Esto comprende, según corresponda:

```text
Alternativas textuales
Nombres de controles
Instrucciones
Mensajes
Errores
Estados
Títulos del documento
```

La aplicación no mantiene una variante lingüística independiente destinada exclusivamente a tecnologías de asistencia.

La información accesible debe corresponder al idioma utilizado por la interfaz o por el contenido al que pertenece.

La representación de nombres personales también forma parte de la localización cuando el proyecto dispone de una representación definida para cada idioma.

Esto permite utilizar las formas y sistemas de escritura correspondientes sin asumir que todos los idiomas comparten una misma representación textual.

## Idioma semántico

El idioma principal del documento corresponde al idioma activo del sistema.

La declaración lingüística del documento se establece después de resolver el idioma activo y se actualiza cuando el usuario selecciona otro idioma.

La navegación interna que conserva el mismo idioma activo no cambia esta declaración.

Conceptualmente:

```text
Idioma activo del sistema
=> idioma principal del documento

Cambio manual de idioma
=> actualizar idioma activo
=> actualizar idioma principal del documento

Navegación interna
=> conservar idioma principal mientras no cambie el idioma activo
```

Cuando el contenido se presenta en el mismo idioma del sistema, utiliza normalmente el contexto lingüístico ya establecido por el documento.

Cuando una variante de contenido se presenta mediante un idioma de respaldo diferente del idioma activo, el documento continúa utilizando el idioma del sistema y la región correspondiente al contenido declara su idioma real.

Conceptualmente:

```text
Idioma del sistema
=> documento
=> interfaz
=> navegación
=> mensajes

Contenido en el mismo idioma
=> utiliza el contexto lingüístico del documento

Contenido en otro idioma
=> declara su propio idioma
=> no cambia el idioma del documento
```

La utilización de un idioma de respaldo no cambia:

```text
Idioma activo
Preferencia
Dirección
Navegación
Idioma de la interfaz
```

El aviso que informa que el contenido se presenta en otro idioma pertenece a la interfaz y continúa utilizando el idioma activo del sistema.

La declaración lingüística correspondiente al contenido debe limitarse a la región que realmente pertenece a esa variante.

Los controles, acciones y demás textos propios de la interfaz que rodean ese contenido continúan perteneciendo al idioma del sistema.

Una colección puede presentar simultáneamente unidades de contenido en idiomas diferentes.

Cada unidad utiliza el idioma correspondiente a la variante que realmente representa.

Conceptualmente:

```text
Colección
|
+-- unidad en idioma del sistema
|   => utiliza contexto del documento
|
+-- unidad en otro idioma
|   => declara idioma propio
|
+-- unidad en otro idioma
    => declara idioma propio
```

La colección completa no adopta el idioma de una unidad particular.

Los textos accesibles que forman parte del contenido, incluidas las alternativas textuales proporcionadas para sus imágenes, pertenecen al mismo contexto lingüístico de la variante representada.

Los encabezados y demás textos del contenido también utilizan el idioma real de esa variante.

Cuando una parte concreta del contenido cambia de idioma dentro de una variante, el cambio debe declararse semánticamente en la región o fragmento correspondiente.

La declaración se aplica a la parte más adecuada de la estructura y no a una región mayor que incluya contenido de otros idiomas.

Conceptualmente:

```text
Contenido
=> idioma de la variante

Fragmento en otro idioma
=> idioma propio del fragmento
```

Los cambios lingüísticos definidos editorialmente deben conservarse durante el procesamiento y la representación del contenido.

El frontend no debe determinar el idioma mediante análisis del texto ni otro tipo de recurso programático.

Cuando una parte utiliza el mismo idioma que su contexto superior, no necesita repetir innecesariamente la declaración lingüística.

Las declaraciones utilizadas siguen las mismas etiquetas de idioma definidas por la arquitectura de internacionalización del sitio.

## Redimensionamiento, reflujo y orientación

El contenido debe conservarse completo y funcional cuando el usuario aumenta el tamaño del texto.

La ampliación no debe producir:

```text
Contenido recortado
Texto truncado
Texto oculto
Superposición
Controles inaccesibles
Pérdida de funcionalidad
```

La escala tipográfica debe responder al tamaño base configurado por el usuario sin perder las proporciones visuales definidas para la aplicación.

Conceptualmente:

```text
Tamaño base del usuario
=> escala tipográfica de la aplicación

Aumento del texto
=> escala aumenta
=> contenedores se adaptan
=> contenido permanece disponible
```

Las dimensiones visuales utilizadas en la presentación normal no constituyen límites rígidos para los componentes que contienen texto.

Cuando el texto necesita más espacio:

```text
Contenedor
=> crece o se reorganiza

Texto
=> permanece completo
```

Los controles que contienen texto también deben adaptarse al redimensionamiento.

Los elementos sin contenido textual mantienen su geometría cuando el aumento del texto no cambia la información ni la funcionalidad que proporcionan.

La aplicación no restringe las capacidades normales del navegador para ampliar la página.

La ampliación y la reducción del espacio disponible deben activar las mismas reglas de reorganización utilizadas por la adaptación responsive.

La interfaz debe conservar el contenido y la funcionalidad cuando alcanza el ancho mínimo exigido por el nivel de accesibilidad establecido para el proyecto.

La página completa no debe requerir desplazamiento horizontal para acceder al contenido normal.

Conceptualmente:

```text
Espacio suficiente
=> composición correspondiente

Espacio reducido
=> reflujo

Reflujo
=> contenido completo
=> funciones completas
=> sin desplazamiento horizontal de la página
```

El desplazamiento horizontal debe limitarse a un componente cuando la estructura bidimensional de ese contenido necesita conservarse para mantener su uso, comprensión o significado.

No debe utilizarse como sustitución general del reflujo.

Las cadenas extensas deben ajustarse dentro de su contenedor cuando su división no altera el significado.

El contenido cuya estructura horizontal necesita conservarse utiliza el tratamiento específico correspondiente a su propio componente.

Los cambios realizados por el usuario sobre el espaciado entre líneas, párrafos, letras o palabras no deben provocar pérdida de contenido ni funcionalidad.

Los contenedores deben crecer o reorganizarse para conservar:

```text
Texto
Controles
Relaciones
Estados
Acciones
```

La aplicación no exige una orientación determinada del dispositivo.

Todo el contenido y todas las funciones permanecen disponibles en las diferentes orientaciones.

El cambio de orientación utiliza las reglas responsive correspondientes al espacio disponible resultante.

Conceptualmente:

```text
Orientación cambia
=> espacio disponible cambia
=> aplicar composición correspondiente
```

No se utiliza:

```text
Bloqueo de orientación
Exigencia de girar el dispositivo
Contenido exclusivo de una orientación
Función exclusiva de una orientación
```

El cumplimiento de estas reglas no implica por sí solo el cumplimiento completo de criterios de nivel superior relacionados con la presentación visual.

Los requisitos adicionales de esos criterios deben evaluarse de forma independiente antes de declarar su cumplimiento.

## Color y contraste

Las combinaciones de color permitidas por el sistema deben mantener el nivel de contraste establecido para el proyecto.

La conformidad implica no escoger una combinación diferente para cada página. Todo el sitio queda con el mismo tema elegido, con sus colores y contrastes, hasta que el usuario lo cambie.

Los temas disponibles forman parte de una misma interfaz y deben mantener el mismo nivel de conformidad.

La garantía de contraste se aplica por separado a cada tema completo.

La existencia de una combinación válida en un tema no permite presuponer que su equivalente en otro tema también sea válida.

Cada tema se evalúa según las combinaciones que debe producir realmente.

Es obligatorio que todos los colores de una paleta puedan combinarse arbitrariamente entre sí. Toda combinación permitida por la presentación debe mantener el contraste correspondiente a la función que desempeña.

Conceptualmente:

```text
Color
+ función
+ superficie permitida
=> combinación validada
```

La comprobación considera el peor caso entre las superficies sobre las que cada color debe utilizarse.

Un color solamente forma parte de una función cuando cumple el requisito correspondiente en todas las superficies permitidas para esa función.

La conformidad se determina mediante el resultado real de la combinación y no mediante el redondeo de un valor inferior hasta el umbral requerido.

Los colores destinados a texto general deben utilizarse sobre las superficies para las que fueron definidos sin perder el nivel de contraste exigido.

Esto comprende las distintas jerarquías de texto utilizadas por la interfaz, incluidos el texto principal, el texto secundario, el texto de menor énfasis y los textos auxiliares utilizados dentro de controles.

Las superficies principales, secundarias y semánticas deben mantener combinaciones válidas con los textos que deben aparecer sobre ellas.

Una superficie utilizada solamente como fondo no necesita satisfacer por sí sola un contraste textual.

El requisito corresponde al texto o a la información visual que se presenta sobre ella.

Conceptualmente:

```text
Superficie
=> debe constituir solamente un fondo

Texto sobre superficie
=> debe mantener el contraste correspondiente
```

Los colores interactivos disponen de combinaciones válidas tanto en su estado normal como en los estados visuales que cambian su apariencia.

Un mismo color no necesita desempeñar simultáneamente funciones incompatibles.

Los colores utilizados como primer plano de texto o iconos deben diferir de los colores utilizados como fondos rellenos cuando sus requisitos de contraste son distintos.

Conceptualmente:

```text
Color de primer plano
=> texto, enlace o icono

Color de fondo
=> superficie de un control

Cada función
=> combinación propia validada
```

Los colores semánticos utilizados para éxito, advertencia, error e información mantienen el contraste exigido en las superficies en las que deben aparecer.

Los estados interactivos asociados a estos colores también deben conservar una combinación válida.

Los enlaces visitados mantienen los mismos requisitos de contraste aplicables a los demás textos interactivos dentro de su contexto.

Los textos auxiliares de los controles, incluidos aquellos presentados antes de introducir un valor, se consideran texto y no quedan excluidos de los requisitos de contraste por utilizar una función secundaria.

Los bordes y demás elementos visuales necesarios para identificar componentes también deben mantener el contraste correspondiente en todas las superficies en las que deben aparecer.

Los componentes que poseen una combinación propia entre primer plano y fondo deben mantener igualmente los requisitos aplicables en todos sus estados.

Esto incluye tanto el contraste del contenido del control respecto de su propio fondo como el contraste visual necesario para reconocer el componente respecto de las superficies que lo rodean.

Conceptualmente:

```text
Contenido del control
+ fondo del control
=> contraste del contenido

Control
+ superficie adyacente
=> contraste necesario para identificarlo
```

Los botones principales mantienen combinaciones válidas entre su contenido y su fondo tanto en estado normal como en los estados que cambian visualmente ese fondo.

Los botones secundarios mantienen una combinación válida para su texto y, cuando su identificación depende de un contorno, también para ese borde respecto de la superficie adyacente.

El indicador de foco utiliza una combinación destinada específicamente a permanecer perceptible sobre las superficies en las que debe aparecer.

Su validación corresponde a información visual funcional y no depende de que el color utilizado alcance los requisitos propios del texto normal.

Los recursos de apoyo visual, las superficies utilizadas por estados y las representaciones de carga conservan las funciones para las que fueron definidas.

Su presencia en la paleta no autoriza reutilizarlos como texto, borde funcional u otra información necesaria cuando esa nueva función no haya sido validada.

La paleta de cada tema queda definida de manera que todos sus usos permitidos mantienen el nivel AA.

La evaluación adicional frente a requisitos de nivel AAA debe registrarse como información técnica.

Algunas combinaciones deben alcanzar también ese nivel superior, pero un elemento no necesita hacerlo para formar parte de la paleta mientras satisfaga el nivel establecido para el proyecto.

## Bordes y separación

Los elementos visuales necesarios para reconocer un componente o comprender su estado utilizan un tratamiento capaz de conservar el contraste correspondiente respecto de las superficies adyacentes.

Una línea puramente decorativa debe utilizar un tratamiento visual diferente cuando su presencia no sea necesaria para identificar un componente, separar información indispensable ni comprender un estado.

Conceptualmente:

```text
Borde funcional
=> identifica componente o estado
=> mantiene contraste funcional

Separador decorativo
=> no transmite información necesaria
=> debe utilizar tratamiento visual propio
```

Un separador decorativo no debe reutilizarse como borde funcional solamente por compartir una función visual semejante.

Si una línea pasa a ser necesaria para reconocer un componente o su estado, utiliza el tratamiento definido para los bordes funcionales.

## Foco visible

Los controles interactivos utilizan un indicador de foco visible que no depende del color propio de cada control para determinar su contraste.

El sistema dispone de un tratamiento de foco definido para permanecer perceptible sobre las superficies en las que debe aparecer.

La indicación debe distinguir el control enfocado sin alterar el orden de navegación ni introducir un segundo estado funcional.

El foco visual acompaña el significado de estados como:

```text
Activo
Seleccionado
Error
Advertencia
```

## Estados semánticos y uso del color

Los colores semánticos funcionan como apoyo visual y no constituyen el único medio utilizado para comunicar un estado.

Conceptualmente:

```text
Color
+ texto o información equivalente
+ estrutura técnica del sitio
=> significado del estado
```

Éxito, advertencia, error e información deben comprenderse aunque el usuario no distinga el color utilizado.

La misma regla se aplica a cualquier estado interactivo o informativo cuyo significado sea necesario para utilizar el sitio.

## Enlaces

Un enlace situado dentro de texto corrido no depende exclusivamente del color para diferenciarse del contenido que lo rodea.

Utiliza una señal visual adicional que permita reconocer su función independientemente de la percepción cromática.

Los enlaces que aparecen como acciones aisladas no deben ser identificados mediante su propio contexto y composición aunque estos permiten reconocer su función interactiva. Algún otro señal, descripción o texto del enlace necesita identificarlos, tecnicamente, estructuralmente y visualmente.

Los diferentes estados de un enlace, incluido el estado visitado, mantienen los requisitos de contraste correspondientes a los contextos en los que deben aparecer.

Los enlaces integrados dentro de texto conservan su forma textual y no adoptan artificialmente la geometría de los controles independientes.

## Colores efectivos

La validación de un color corresponde al resultado visual realmente presentado.

La aplicación de transparencia, superposición, gradiente u otro tratamiento que modifique el color final requiere conservar los mismos requisitos de contraste.

Conceptualmente:

```text
Color validado sin cambio
=> conserva la combinación prevista

Color visualmente cambiado
=> evaluar el resultado efectivo
```

Un valor no se considera automáticamente equivalente al color validado cuando su representación final ha cambiado.

Los fondos fotográficos o variables se consideran según el color efectivo que debe quedar inmediatamente detrás del contenido.

No se presupone que una fotografía concreta mantendrá por sí sola el contraste necesario.

## Contraste de la cabecera

El texto presentado sobre el fondo visual de la cabecera debe conservar el contraste correspondiente independientemente de la luminosidad de la fotografía utilizada.

El tema oscuro incorpora una capa de contraste detrás de la región ocupada por el texto de la cabecera.

Esta capa debe ser suficiente para conservar el nivel AA incluso cuando el área original de la fotografía situada detrás del texto alcance su máxima luminosidad posible.

Conceptualmente:

```text
Fotografía
+ capa de contraste
+ texto de cabecera
=> combinación garantizada
```

La garantía pertenece al tratamiento de la interfaz y no a las características particulares de una fotografía concreta.

Por este motivo, la sustitución futura de la imagen no debe exigir volver a depender visualmente de que una determinada zona de la fotografía sea oscura.

La capa cubre completamente la región ocupada por el bloque textual.

Debe disminuir progresivamente fuera de esa región cuando ello forme parte de la composición visual, pero no debe reducirse dentro del espacio utilizado por el texto hasta perder la garantía establecida.

El nombre y la descripción breve utilizan un color de texto validado para esta combinación.

La diferencia de tamaño entre ambos textos no se utiliza para permitir una combinación insuficiente para texto normal.

De esta manera, el texto de la cabecera conserva el nivel AA tanto en su estado expandido como en cualquier composición en la que permanezca superpuesto al fondo visual.

## Título del documento

Cada página debe disponer de un título de documento que describa su contenido o propósito.

Durante la navegación interna, el título del documento se actualiza para corresponder a la página activa.

El título se localiza de acuerdo con el idioma activo.

En las páginas internas y en los recursos individuales, la información específica de la página aparece antes de la identificación general del sitio.

La página inicial utiliza la identificación localizada del sitio.

Conceptualmente:

```text
Página inicial
=> nombre localizado del sitio

Página interna
=> título localizado de la página
=> nombre localizado del sitio

Recurso individual
=> nombre o título localizado del recurso
=> nombre localizado del sitio
```

El nombre del sitio identifica el portafolio y utiliza la representación localizada del nombre personal correspondiente al idioma activo.

Cuando cambia el idioma, cambia también el título completo de acuerdo con esa localización.

## Cambio de página y foco

La carga inicial del sitio conserva el comportamiento normal de foco del navegador.

La existencia de una región principal o de un encabezado no provoca por sí sola un desplazamiento programático del foco.

Cuando la navegación interna sustituye la página actual por otra página conceptual, el cambio debe proporcionar contexto equivalente al comienzo de una nueva página.

Después de que la nueva página haya sido representada, el foco pasa a su encabezado principal.

Conceptualmente:

```text
Carga inicial
=> conservar comportamiento normal de foco

Navegación interna hacia una nueva página
=> actualizar contexto del documento
=> representar la nueva página
=> situar el foco en su encabezado principal
```

El encabezado principal debe admitir foco programático sin convertirse por ello en una parada adicional dentro del recorrido normal mediante teclado.

Después de recibir el foco como consecuencia de una navegación, el recorrido posterior continúa según el orden natural de los elementos interactivos de la nueva página.

El movimiento de foco se encuentra vinculado al cambio completo de página y no a cualquier actualización de la interfaz.

No desplazan automáticamente el foco:

```text
Carga o sustitución de datos dentro de la misma página
Finalización de un estado de carga
Aparición de un estado vacío dentro de una unidad
Aparición de un error dentro de una unidad
Apertura o cierre de un grupo expandible
Cambio de tema
Cambios de dirección que no sustituyen la página conceptual
```

En estos casos, el foco permanece en el elemento correspondiente a la interacción actual o conserva su posición cuando no existe una acción que justifique cambiarla.

La región principal continúa cumpliendo una función semántica y no se convierte en destino de foco solamente porque cambie la página.

El encabezado principal proporciona el contexto inmediato de la nueva página.

El título del documento proporciona el contexto general correspondiente a esa misma página.

Conceptualmente:

```text
Título del documento
=> identifica la página

Encabezado principal enfocado
=> identifica el nuevo contenido

Región principal
=> delimita semánticamente el contenido
```

No se añade un anuncio independiente que repita el cambio de página cuando el título del documento y el encabezado principal ya proporcionan el contexto necesario.

Una página de contenido no encontrado se considera igualmente una página resultante de la navegación.

Cuando se alcanza mediante navegación interna, su encabezado principal recibe el foco después de que la página haya sido representada.

En las composiciones donde la navegación se encuentra temporalmente expandida, la selección de un destino completa primero la transición de navegación correspondiente y después sitúa el foco en el encabezado principal de la nueva página.

De esta manera, el foco no permanece asociado a un control perteneciente a una representación de navegación que dejó de estar disponible después del cambio.

## Pruebas de accesibilidad

La accesibilidad se valida mediante una combinación obligatoria de pruebas automatizadas y comprobaciones manuales.

La automatización verifica aquello que debe determinarse de forma objetiva mediante la estructura de la aplicación, el comportamiento programático y la representación producida por el navegador.

La comprobación manual se utiliza para los aspectos cuya corrección depende también de la percepción, del significado o de la experiencia real de interacción.

La aprobación de la auditoría automática no sustituye las comprobaciones manuales aplicables.

Conceptualmente:

```text
Comprobaciones automatizadas
+ comprobaciones manuales aplicables
=> evaluación de accesibilidad

Solamente comprobaciones automatizadas
=> evaluación incompleta
```

La auditoría automatizada se ejecuta mediante las mismas pruebas de navegador utilizadas por los flujos completos de la aplicación.

Una violación detectada por la auditoría automática produce una prueba fallida.

Los resultados que una herramienta no debe determinar de forma concluyente no se consideran automáticamente conformes y permanecen sujetos a comprobación manual.

La batería automatizada debe cubrir las reglas de accesibilidad correspondientes al nivel definido para el proyecto y los requisitos adicionales adoptados expresamente.

La cobertura se organiza por:

```text
Tipo de página
Estructura
Componente
Estado
Composición
Tema
Contexto lingüístico
Forma de interacción
```

No es necesario repetir una prueba completa para cada elemento editorial individual cuando varios elementos utilizan exactamente la misma estructura y comportamiento.

Cada tipo conceptual de página debe disponer de cobertura.

Esto comprende las páginas iniciales, las páginas generales, los listados, los diferentes tipos de detalle, los formularios y los estados de contenido no encontrado.

Los estados que cambian la estructura o la semántica deben comprobarse también en su propia condición.

Esto comprende:

```text
Carga
Contenido disponible
Contenido vacío
Error
Contenido no encontrado
Formulario normal
Envío en curso
Validación
Confirmación
Límite de envíos
Fallo de envío
```

Las pruebas de accesibilidad deben contemplar los diferentes temas cuando la comprobación depende de la representación visual.

También deben contemplar las diferentes situaciones lingüísticas cuando la semántica depende del idioma del sistema, del idioma del contenido o de un cambio lingüístico interno.

Las comprobaciones automatizadas deben cubrir, cuando corresponda:

```text
Estructura semántica
Jerarquía
Nombres de controles
Etiquetas
Relaciones accesibles
Estados accesibles
Elementos ocultos
Orden y comportamiento de foco
Navegación mediante teclado
Cambios de página
Idioma semántico
Contenido con idioma diferente al sistema
Cambios lingüísticos internos
Presencia y conservación de alternativas textuales
Combinaciones de contraste determinables
Uso complementario del color
Redimensionamiento del texto
Reflujo
Ausencia de desplazamiento horizontal indebido
Adaptación del espaciado textual
Orientación
Tamaño y superficie de objetivos interactivos
Interacción mediante diferentes mecanismos de entrada
Ausencia de dependencia funcional del paso del puntero
Cancelación de acciones de puntero
Ausencia de arrastre obligatorio
Estados de carga
Estados del formulario
Mensajes de progreso
Resultados del formulario
```

Las comprobaciones manuales deben cubrir, cuando corresponda:

```text
Recorrido completo mediante teclado
Orden lógico del foco
Visibilidad y claridad del indicador de foco
Ausencia de obstáculos sobre el foco
Coherencia entre estructura visual y estructura semántica
Adecuación de nombres accesibles
Correspondencia entre el idioma declarado y el contenido real
Adecuación de cambios lingüísticos internos
Calidad de las alternativas textuales
Clasificación correcta de imágenes según su función
Contraste en composiciones variables
Comprensión de estados sin depender solamente del color
Redimensionamiento visual del texto
Zoom real del navegador
Reflujo visual
Legibilidad con espaciado modificado
Uso real mediante puntero y tacto
Cancelación práctica de interacciones
Comunicación mediante tecnologías de asistencia
Navegación mediante tecnologías de asistencia
Comunicación de cambios de página
Comunicación de estados del formulario
Comunicación de carga, resultados y errores
```

La validación automática del foco debe comprobar qué elemento recibe el foco, cuándo se conserva y cuándo cambia según las reglas de navegación definidas.

La comprobación manual debe confirmar además que el foco resulta perceptible y que su recorrido mantiene un sentido coherente para la persona usuaria. Esta comprobación no impide el flujo automatizado de la promoción.

La validación automática del idioma debe comprobar que el documento y las regiones correspondientes disponen del contexto lingüístico esperado.

La comprobación manual debe confirmar que la declaración corresponde realmente al contenido presentado y que los cambios internos se encuentran aplicados a la región adecuada. Esta comprobación no impide el flujo automatizado de la promoción.

La validación automática de las alternativas textuales debe comprobar la presencia de la alternativa, la conservación del valor recibido y las diferencias esperadas entre representaciones.

La comprobación manual debe determinar si la alternativa describe adecuadamente la función real de la imagen. Esta comprobación no impide el flujo automatizado de la promoción.

El contraste debe comprobarse automáticamente siempre que las combinaciones puedan determinarse de forma objetiva.

Las composiciones cuyo resultado depende de fondos variables, superposiciones u otras condiciones visuales requieren también comprobación manual de la implementación final. Esta comprobación no impide el flujo automatizado de la promoción.

Las reglas de redimensionamiento, reflujo y espaciado deben comprobarse automáticamente mediante escenarios que alteren el espacio disponible y las condiciones tipográficas.

La comprobación manual debe confirmar además que la representación continúa siendo legible, utilizable y libre de recortes, superposiciones o pérdidas visuales. Esta comprobación no impide el flujo automatizado de la promoción.

Los objetivos interactivos deben poder medirse automáticamente mediante la representación final producida por el navegador.

La comprobación manual debe confirmar que la superficie percibida y utilizada corresponde realmente al control esperado y que la interacción resulta adecuada mediante tacto y puntero. Esta comprobación no impide el flujo automatizado de la promoción.

Los comportamientos de teclado, puntero, tacto y demás mecanismos de entrada deben compartir la misma funcionalidad.

La automatización debe comprobar los recorridos y resultados que puedan reproducirse de forma determinista.

La comprobación manual debe confirmar que no existen comportamientos difíciles de descubrir o utilizar que no sean identificados por la prueba programática. Esta comprobación no impide el flujo automatizado de la promoción.

Las tecnologías de asistencia requieren comprobación manual de la experiencia real. Esta comprobación no impide el flujo automatizado de la promoción.

La automatización puede validar la semántica que estas tecnologías consumen, pero no sustituye la comprobación de cómo se comunican realmente:

```text
Regiones
Encabezados
Nombres
Estados
Cambios de página
Idiomas
Alternativas
Formularios
Validaciones
Progreso
Confirmaciones
Advertencias
Errores
```

La aceptación automatizada exige que la totalidad de las pruebas automatizadas termine correctamente.

No se utiliza una puntuación aproximada de accesibilidad como sustitución de las pruebas.

El porcentaje de aceptación corresponde a la proporción real de pruebas automatizadas aprobadas y solamente resulta aceptable cuando la suite completa se encuentra aprobada.

Conceptualmente:

```text
Suite automatizada completa aprobada
=> aceptación automatizada

Cualquier prueba automatizada fallida
=> sin aceptación
```

Las comprobaciones manuales aplicables también deben completarse satisfactoriamente antes de promover un cambio que modifique estructura, semántica, interacción, navegación, estados, representación accesible o contenido cuya accesibilidad dependa de una decisión editorial. Esta comprobación no impide el flujo automatizado de la promoción.

