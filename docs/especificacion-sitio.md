# Especificación técnica de identidad visual

## Estado

Esta especificación define la identidad visual base del frontend de `sitio`.

La especificación fue derivada de las decisiones de diseño tomadas durante la definición visual del proyecto y de las representaciones finales aprobadas para los temas claro y oscuro.

Su objetivo es servir como referencia técnica durante la implementación con Angular y Tailwind CSS y durante las etapas posteriores de accesibilidad e implementación.

Los valores contenidos aquí deben considerarse la base concreta de implementación.

Los ajustes posteriores deben responder a una necesidad real detectada durante el desarrollo, no a una reinterpretación arbitraria de la identidad visual.

---

# Principios generales

La identidad visual del sitio debe transmitir una apariencia:

- formal;
- sobria;
- clásica;
- tecnológica;
- personal;
- estructurada;
- sin dependencia de modas visuales;
- sin redondeos decorativos por defecto;
- con uso contenido de sombras;
- con rojo como color principal;
- con verde como color secundario;
- con una combinación de tipografía serif y sans-serif.

La fotografía personal forma parte de la identidad visual del sitio y cumple también la función que normalmente podría cumplir un logotipo.

No existe un logotipo independiente.

La cabecera combina:

- Fondo visual y foto juntos;
- nombre;
- descripción breve.

La navegación utiliza iconografía como apoyo visual.

Las páginas reutilizan una misma estructura global y un mismo lenguaje visual.

Las diferencias entre páginas se concentran dentro de la región de contenido correspondiente.

Las tarjetas forman parte del lenguaje visual común del sitio, aunque cada tipo de elemento conserva sus propios datos y estructura interna.

El tema claro y el tema oscuro mantienen la misma identidad, estructura, contenido, jerarquía y disposición para una misma composición responsive.

El cambio de tema solamente modifica la representación visual correspondiente a cada paleta.

La estructura del sitio se adapta al espacio disponible sin convertir las composiciones estrechas en una reducción proporcional de la representación de escritorio.

La adaptación responsive debe conservar el contenido, la jerarquía, la identidad visual, los estados y el orden editorial.

---

# 1. Tipografía

## 1.1. Títulos

Los títulos utilizan una tipografía serif de alto contraste y carácter editorial.

```css
font-family:
    "Noto Serif Display",
    "Cormorant Garamond",
    "Georgia",
    "serif";
```

Orden de preferencia:

1. `Noto Serif Display`
2. `Cormorant Garamond`
3. `Georgia`
4. `serif`

La tipografía serif se utiliza principalmente en:

- nombre principal;
- títulos de página;
- títulos de sección;
- subtítulos importantes;
- citas;
- encabezados destacados.

---

## 1.2. Cuerpo e interfaz

El cuerpo y la interfaz utilizan una tipografía sans-serif limpia y neutra.

```css
font-family:
    "Inter",
    "Noto Sans",
    "Arial",
    "sans-serif";
```

Orden de preferencia:

1. `Inter`
2. `Noto Sans`
3. `Arial`
4. `sans-serif`

La tipografía sans-serif se utiliza principalmente en:

- navegación;
- párrafos;
- controles;
- botones;
- metadatos;
- etiquetas;
- listados;
- selector de idioma;
- selector de tema.

---

# 2. Escala tipográfica

La aplicación utiliza dos escalas tipográficas.

No existe una tercera escala intermedia.

Tampoco se utiliza escalado tipográfico continuo para transformar progresivamente una escala en la otra.

---

## 2.1. Escritorio

Se utiliza cuando:

```text
ancho >= 1024px
```

| Elemento                     | Tamaño |
| ---------------------------- | -----: |
| Nombre principal en cabecera | `64px` |
| H1                           | `48px` |
| H2                           | `36px` |
| H3                           | `28px` |
| H4                           | `22px` |
| Texto destacado / lead       | `18px` |
| Texto base                   | `16px` |
| Texto secundario             | `14px` |
| Texto auxiliar / etiquetas   | `12px` |

---

## 2.2. Pantallas estrechas

Se utiliza cuando:

```text
ancho < 1024px
```

| Elemento                     | Tamaño |
| ---------------------------- | -----: |
| Nombre principal en cabecera | `40px` |
| H1                           | `32px` |
| H2                           | `28px` |
| H3                           | `24px` |
| H4                           | `20px` |
| Texto destacado / lead       | `18px` |
| Texto base                   | `16px` |
| Texto secundario             | `14px` |
| Texto auxiliar / etiquetas   | `12px` |

La escala cambia en el punto de ruptura correspondiente.

No se utiliza `clamp()` para producir una transición continua entre ambas escalas.

---

# 3. Alturas de línea

| Elemento         | `line-height` |
| ---------------- | ------------: |
| Nombre principal |           `1` |
| H1               |        `1.05` |
| H2               |         `1.1` |
| H3               |        `1.15` |
| Lead             |        `1.35` |
| Texto base       |         `1.5` |
| Texto secundario |        `1.45` |
| Texto auxiliar   |         `1.4` |

Regla general:

- los títulos deben permanecer relativamente compactos;
- los textos de lectura deben disponer de mayor espacio vertical;
- la navegación debe utilizar una densidad ligeramente mayor que el cuerpo principal.

---

# 4. Pesos tipográficos

| Elemento                      | Peso  |
| ----------------------------- | ----: |
| Nombre principal              | `700` |
| H1                            | `700` |
| H2                            | `700` |
| H3                            | `600` |
| Lead                          | `500` |
| Texto base                    | `400` |
| Texto secundario              | `400` |
| Etiquetas pequeñas            | `600` |
| Navegación principal          | `500` |
| Elemento activo de navegación | `600` |
| Botones                       | `600` |

---

# 5. Paleta del tema claro

## 5.1. Colores neutrales

| Uso                   | Color     |
| --------------------- | --------- |
| Fondo principal       | `#F6F3EE` |
| Superficie primaria   | `#FFFFFF` |
| Superficie secundaria | `#F1ECE5` |
| Texto principal       | `#141414` |
| Texto secundario      | `#5E6167` |
| Texto tenue           | `#676B72` |
| Borde                 | `#7A7E85` |

El mismo token de borde se utiliza para los bordes estructurales, bordes de controles y separadores cuando una línea resulta necesaria.

---

## 5.2. Colores de identidad

| Uso                    | Color     |
| ---------------------- | --------- |
| Rojo principal         | `#B51E23` |
| Rojo hover             | `#99181C` |
| Rojo suave / selección | `#F7E9E8` |
| Verde principal        | `#2F6D59` |
| Verde hover            | `#255847` |
| Verde suave            | `#E8F2EE` |

---

## 5.3. Colores de apoyo

| Uso            | Color     |
| -------------- | --------- |
| Negro de apoyo | `#0E0E0E` |
| Blanco puro    | `#FFFFFF` |

---

# 6. Paleta del tema oscuro

## 6.1. Colores neutrales

| Uso                   | Color     |
| --------------------- | --------- |
| Fondo principal       | `#0F141B` |
| Superficie primaria   | `#141B24` |
| Superficie secundaria | `#18212C` |
| Texto principal       | `#F2F1EE` |
| Texto secundario      | `#B8BDC6` |
| Texto tenue           | `#8E97A3` |
| Borde funcional       | `#737B8B` |
| Separador decorativo  | `#202936` |

`#737B8B` se utiliza cuando una línea resulta necesaria para reconocer un componente, comprender un estado o proporcionar una separación estructural que necesita ser percibida.

`#202936` se reserva para separadores puramente decorativos cuya presencia no constituye información necesaria.

Un separador que pase a desempeñar una función necesaria debe utilizar el valor de borde funcional.

---

## 6.2. Colores de identidad

| Uso                          | Color     |
| ---------------------------- | --------- |
| Rojo interactivo             | `#FE6162` |
| Rojo interactivo hover       | `#FE686A` |
| Rojo de fondo principal      | `#D6363B` |
| Rojo de fondo hover          | `#C92F35` |
| Rojo suave / selección       | `#3A1618` |
| Verde principal              | `#58B28D` |
| Verde hover                  | `#4FA683` |
| Verde suave                  | `#173328` |

El rojo utilizado como primer plano y el rojo utilizado como fondo de controles mantienen funciones distintas.

Los valores de primer plano se utilizan cuando el rojo aparece como texto, enlace, icono o información equivalente.

Los valores de fondo se utilizan en componentes rellenos que presentan texto claro sobre la superficie roja.

No debe intercambiarse un valor entre estas funciones sin comprobar nuevamente el contraste resultante.

---

## 6.3. Colores de apoyo

| Uso           | Color     |
| ------------- | --------- |
| Casi negro    | `#0A0E13` |
| Blanco cálido | `#F7F5F1` |

---

## 6.4. Colores auxiliares accesibles

| Uso              | Color     |
| ---------------- | --------- |
| Enlace visitado  | `#BB7FD3` |
| Foco             | `#E2484D` |
| Placeholder      | `#8E97A3` |
| Base de skeleton | `#18212C` |

---

# 7. Estados visuales

## 7.1. Tema claro

### Enlaces

```text
normal        => #B51E23
hover         => #99181C
visited       => #7C3A65
focus outline => #141414
```

### Botón principal

```text
fondo normal => #B51E23
fondo hover  => #99181C
texto        => #FFFFFF
```

### Botón secundario

```text
fondo => #FFFFFF
borde => #7A7E85
texto => #141414
```

### Navegación activa

```text
fondo           => #F7E9E8
barra izquierda => #B51E23
texto           => #B51E23
```

---

## 7.2. Tema oscuro

### Enlaces

```text
normal        => #FE6162
hover         => #FE686A
visited       => #BB7FD3
focus outline => #E2484D
```

### Botón principal

```text
fondo normal => #D6363B
fondo hover  => #C92F35
texto        => #FFFFFF
```

### Botón secundario

```text
fondo => transparent
borde => #737B8B
texto => #F2F1EE
```

### Navegación activa

```text
fondo           => #3A1618
barra izquierda => #D6363B
texto           => #F2F1EE
```

---

## 7.3. Estados semánticos

### Tema claro

| Estado      | Color     |
| ----------- | --------- |
| Éxito       | `#2F6D59` |
| Advertencia | `#8F6112` |
| Error       | `#B51E23` |
| Información | `#365E96` |

### Tema oscuro

| Estado      | Color     |
| ----------- | --------- |
| Éxito       | `#58B28D` |
| Advertencia | `#D6A34A` |
| Error       | `#FE6162` |
| Información | `#6FA8FF` |

---

## 7.4. Foco

Todos los elementos interactivos deben disponer de foco visible.

La geometría del indicador es:

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

El tratamiento funcional del foco permanece igual entre temas.

Cada valor cromático conserva el contraste necesario sobre las superficies permitidas de su propio tema.

---

# 8. Sombras

Las sombras deben utilizarse para producir profundidad y separación visual.

No deben convertirse en decoración permanente de todos los elementos.

## 8.1. Tema claro

### Sombra ligera

```css
box-shadow: 0 4px 12px rgba(17, 17, 17, 0.06);
```

### Sombra media

```css
box-shadow: 0 8px 24px rgba(17, 17, 17, 0.10);
```

### Cabecera compacta o elemento sticky

```css
box-shadow: 0 6px 18px rgba(17, 17, 17, 0.12);
```

---

## 8.2. Tema oscuro

### Sombra ligera

```css
box-shadow: 0 4px 14px rgba(0, 0, 0, 0.24);
```

### Sombra media

```css
box-shadow: 0 10px 26px rgba(0, 0, 0, 0.34);
```

### Cabecera compacta o elemento sticky

```css
box-shadow: 0 8px 24px rgba(0, 0, 0, 0.40);
```

---

## 8.3. Uso previsto

Las sombras deben utilizarse en:

- paneles;
- navegación sticky;
- cabecera compacta;
- elementos destacados;
- tarjetas;
- controles importantes.

No deben utilizarse de forma indiscriminada en cada bloque de contenido.

---

# 9. Bordes

## 9.1. Border radius

El valor base es:

```css
border-radius: 0;
```

El redondeo no forma parte de la identidad visual principal.

Si algún elemento concreto requiere un radio por razones funcionales o visuales, deberá definirse expresamente.

---

## 9.2. Espesores

```text
Borde estándar  => 1px
Separador       => 1px
Línea de acento => 3px
```

---

## 9.3. Tema claro

```text
Borde         => #7A7E85
Acento rojo   => #B51E23
Acento verde  => #2F6D59
```

El valor `#7A7E85` se utiliza tanto para bordes como para separadores cuando la composición requiere una línea.

---

## 9.4. Tema oscuro

```text
Borde funcional      => #737B8B
Separador decorativo => #202936
Acento rojo          => #D6363B
Acento verde         => #58B28D
```

`#737B8B` se utiliza en bordes de controles y en cualquier línea necesaria para reconocer un componente, un estado o una separación estructural.

`#202936` solamente debe utilizarse cuando la línea es decorativa y su ausencia no modifica la comprensión ni la identificación de un componente.

---

## 9.5. Regla visual

No todos los elementos deben estar encerrados en cajas.

La separación entre regiones debe priorizar:

1. espaciado;
2. alineación;
3. cambio de superficie;
4. separadores;
5. bordes solamente cuando aporten información estructural.

---

# 10. Espaciado

La escala base de espaciado es:

```text
4px
8px
16px
24px
32px
48px
64px
```

---

## 10.1. Aplicación

| Uso                                    | Espacio |
| -------------------------------------- | ------: |
| Padding general de escritorio          |  `24px` |
| Padding general en pantallas estrechas |  `16px` |
| Separación navegación / contenido      |  `24px` |
| Padding interno de navegación          |  `16px` |
| Separación entre bloques de navegación |  `24px` |
| Separación entre elementos de menú     |  `12px` |
| Separación idioma / tema               |  `16px` |
| Padding de paneles                     |  `16px` |
| Gap entre columnas principales         |  `24px` |
| Gap entre tarjetas pequeñas            |  `16px` |
| Título / párrafo                       |  `12px` |
| Párrafo / párrafo                      |  `16px` |
| Secciones mayores                      |  `32px` |
| Grupos grandes                         |  `48px` |

El padding general utiliza:

```text
ancho >= 1024px
=> 24px

ancho < 1024px
=> 16px
```

No se reduce a `8px` como regla general para pantallas estrechas.

El cambio de composición no implica reducir automáticamente el espaciado vertical.

Los valores de separación definidos para paneles, tarjetas, párrafos, secciones y grupos se conservan mientras no exista una necesidad específica de reorganización.

---

# 11. Proporciones del layout

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

## 11.1. Escritorio

Mientras la composición de escritorio permanece activa:

### Navegación

```text
224px
```

Ancho fijo.

No se reduce progresivamente dentro del escritorio.

### Columna principal

```text
mínimo => 720px
óptimo => 1fr
```

### Área de exposición de Inicio

```text
320px
```

Ancho fijo cuando se utiliza como columna lateral.

### Ancho máximo del contenido interior principal

```text
960px
```

### Ancho máximo total previsto

```text
1504px
```

---

## 11.2. Inicio en escritorio amplio

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

## 11.3. Inicio en escritorio intermedio

Cuando:

```text
1024px <= ancho < 1360px
```

la navegación lateral continúa utilizando:

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

## 11.4. Páginas internas en escritorio

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

## 11.5. Composición estrecha

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

---

## 11.6. Pie

El sitio no dispone de pie global.

El contenido termina cuando termina la página.

---

# 12. Cabecera

La cabecera es una única composición visual.

Incluye:

- Fondo visual y foto juntos;
- nombre;
- descripción breve.

`Fondo visual y foto juntos` no debe volver a dividirse visualmente en un fondo y una fotografía tratados como elementos independientes.

Las representaciones de la cabecera no deben incorporar frases de efecto, lemas, citas ni otros textos adicionales que no formen parte del contenido definido.

---

## 12.1. Estado expandido en escritorio

Cuando:

```text
ancho >= 1024px
```

utiliza:

```text
altura             => 320px
padding horizontal => 32px
padding vertical   => 24px
```

Debe mostrar:

- Fondo visual y foto juntos;
- nombre;
- descripción breve.

---

## 12.2. Estado compacto en escritorio

Cuando:

```text
ancho >= 1024px
```

utiliza:

```text
altura             => 112px
padding horizontal => 24px
padding vertical   => 16px
```

Debe mantener:

- Fondo visual y foto juntos;
- nombre.

Debe ocultar:

- descripción breve.

---

## 12.3. Comportamiento

Al desplazarse la página:

```text
cabecera expandida
        |
        V
cabecera compacta
```

La identidad personal nunca desaparece completamente.

---

## 12.4. Pantallas estrechas

Cuando:

```text
ancho < 1024px
```

la cabecera mantiene la misma identidad y los mismos estados conceptuales.

El estado expandido presenta:

```text
Fondo visual y foto juntos
Nombre
Descripción breve
```

El estado compacto presenta:

```text
Fondo visual y foto juntos
Nombre
```

La descripción breve deja de mostrarse en el estado compacto.

La cabecera no utiliza obligatoriamente las alturas rígidas de `320px` y `112px`.

Su altura deriva de:

```text
Contenido
Padding
Ancho disponible
```

La fotografía permanece integrada en `Fondo visual y foto juntos`.

No se convierte en un avatar circular.

No desaparece completamente en el estado compacto.

---

## 12.5. Contraste de la cabecera en el tema oscuro

El nombre y la descripción breve utilizan:

```text
#F2F1EE
```

cuando se representan sobre el fondo visual de la cabecera.

La región situada detrás del bloque textual utiliza una capa negra con:

```text
rgba(0, 0, 0, 0.60)
```

como opacidad mínima efectiva.

La capa cubre completamente la zona ocupada por el texto.

debe degradarse hacia una opacidad menor o hacia transparencia fuera de esa región.

No debe reducirse dentro del área ocupada por el nombre o por la descripción breve.

Conceptualmente:

```text
Fotografía
        |
        V
Capa negra >= 60%
        |
        V
Texto #F2F1EE
```

La garantía se calcula suponiendo el caso más luminoso posible detrás del texto.

Un fondo original:

```text
#FFFFFF
```

después de una capa negra al `60%` produce como peor fondo efectivo:

```text
#666666
```

El contraste resultante es:

```text
#F2F1EE sobre #666666
=> 5.0834876786:1
```

El resultado supera:

```text
4.5:1
```

y permite que tanto el nombre como la descripción breve satisfagan AA sin depender de que el texto pueda considerarse grande.

La regla se conserva en cualquier composición donde el texto permanezca superpuesto a la fotografía.

La sustitución futura de la fotografía no modifica esta garantía mientras permanezcan el color del texto y la capa mínima establecida.

---

# 13. Navegación

## 13.1. Dimensiones de escritorio

Cuando:

```text
ancho >= 1024px
```

la navegación utiliza:

```text
ancho                      => 224px
padding superior           => 16px
padding lateral            => 16px
gap controles / menú       => 20px
altura de ítem principal   => 48px
padding horizontal de ítem => 16px
gap icono / texto          => 12px
sangría de subítems        => 32px
altura de subítem          => 36px
gap entre subítems         => 8px
altura máxima visible      => 100vh
overflow vertical          => auto
```

El ancho de `224px` permanece fijo mientras la navegación lateral continúa activa.

---

## 13.2. Estructura de escritorio

La navegación comienza con los controles globales:

```text
Idioma | Tema
```

Después aparece el bloque de accesos directos:

```text
Inicio
Sobre mí
Contactos
```

No existen separadores entre estos tres elementos.

Después de `Contactos` existe una separación visual respecto de las secciones de contenido.

Las secciones de contenido son:

```text
Certificaciones
Proyectos
Artículos
```

Cada una debe representar contenido subordinado.

Las secciones de contenido mantienen líneas divisorias que permiten distinguir visualmente un grupo del siguiente.

Conceptualmente:

```text
Idioma | Tema
----------------

Inicio
Sobre mí
Contactos
----------------

Certificaciones
    ...
----------------

Proyectos
    ...
----------------

Artículos
    ...
```

---

## 13.3. Jerarquía expandible

Las secciones con contenido subordinado deben expandirse y contraerse.

Ejemplo:

```text
Proyectos
    Proyecto
    Proyecto
    ...
    Ver todos los proyectos
```

El acceso al listado completo siempre aparece al final de los elementos mostrados.

No debe aparecer antes de los elementos representados.

El texto del acceso debe indicar explícitamente cuál es su destino.

Conceptualmente:

```text
Ver todos los proyectos

Ver todos los artículos

Ver todas las certificaciones
```

---

## 13.4. Cantidad de elementos

La navegación no debe contener listas completas potencialmente ilimitadas.

Debe mostrar solamente una cantidad limitada de elementos representativos.

La cantidad mostrada no constituye una restricción estructural fija.

El componente debe admitir variaciones en la cantidad de elementos sin alterar la estructura general de la navegación.

El acceso al listado completo permite continuar hacia la página correspondiente.

---

## 13.5. Overflow de escritorio

Si la navegación lateral supera la altura disponible de la pantalla:

```css
overflow-y: auto;
```

El desplazamiento interno es una protección estructural.

No debe utilizarse como justificación para insertar listas ilimitadas.

---

## 13.6. Posicionamiento

La navegación permanece disponible durante el desplazamiento mediante comportamiento sticky.

En escritorio se aplica a la navegación lateral.

En pantallas estrechas se aplica a la composición superior formada por la cabecera compacta y la barra de navegación móvil.

---

## 13.7. Estado activo

Los accesos directos se marcan como activos en su propia página.

Las secciones que contienen elementos permanecen activas tanto en su listado como en sus páginas individuales.

Cuando se representa el detalle de un elemento y su sección se encuentra expandida, el elemento seleccionado también debe disponer de estado activo.

Conceptualmente:

```text
Listado de proyectos
=> Proyectos activo

Proyecto concreto
=> Proyectos activo
=> Proyecto seleccionado activo

Listado de certificaciones
=> Certificaciones activo

Certificado o certificación concreta
=> Certificaciones activo
=> Elemento seleccionado activo

Listado de artículos
=> Artículos activo

Artículo concreto
=> Artículos activo
=> Artículo seleccionado activo
```

---

## 13.8. Navegación en pantallas estrechas

Cuando:

```text
ancho < 1024px
```

la navegación lateral deja de utilizarse.

Inmediatamente debajo de la cabecera aparece una barra formada por:

```text
Menú | Idioma | Tema
```

Idioma y Tema permanecen directamente accesibles.

No se introducen dentro de una sección adicional de configuración o de menú.

Al activar `Menú`, la navegación aparece debajo de esta barra.

La navegación forma parte del flujo normal del documento.

No se utiliza:

```text
drawer lateral
overlay
panel flotante sobre el contenido
```

Conceptualmente:

Sin expansión del menú:

```text
Cabecera
Menú | Idioma | Tema
Contenido
```


Con expansión del menú:

```text
Cabecera
Menú | Idioma | Tema
Navegación expandida
Contenido
```

La apertura de la navegación desplaza el contenido hacia abajo.

Al cerrarla, el espacio correspondiente deja de formar parte del flujo, regresando al estado "Sin expansión del menú".

---

## 13.9. Estructura del menú en pantallas estrechas

Los accesos directos permanecen como destinos normales:

```text
Inicio
Sobre mí
Contactos
```

Las secciones con elementos subordinados permanecen como grupos expandibles:

```text
Certificaciones
Proyectos
Artículos
```

Cuando un grupo está cerrado:

```text
IconChevronDown
```

Al activar el grupo:

```text
IconChevronDown
=> IconChevronUp

grupo
=> abierto
```

Solamente el grupo activado permanece abierto.

Si más de uno grupo fuera abierto, todos los grupos abiertos se mantienen hasta que el usuario decida cerrálos.

Abrir un grupo no cierra otro automaticamente, eso depende de la decisión del usuario.

Cuando el grupo ya está abierto y vuelve a activarse, el comportamiento es cerrarlo:

```text
IconChevronUp
=> IconChevronDown

grupo
=> cerrado
```

Esta acción cierra solamente el grupo y no realiza navegación hacia un elemento concreto.

La misma regla se aplica a cualquier sección de navegación que utilice estados abierto y cerrado.

Los iconos `IconChevronDown` y `IconChevronUp` forman parte del control de la sección, no constituyen controles independientes.

---

## 13.10. Navegación desde el menú estrecho

Cuando se selecciona un elemento concreto dentro de un grupo:

```text
elemento
=> navegar

Grupo
=> estado cerrado
=> IconChevronDown

Menú
=> cerrado
```

Cuando se selecciona un acceso directo:

```text
Destino
=> navegar

Menú
=> cerrado
```

El menú no permanece abierto después de completar la selección del destino.

La barra:

```text
Menú | Idioma | Tema
```

continúa disponible durante el desplazamiento junto con la cabecera compacta.

---

# 14. Foto y composición de cabecera

La fotografía no utiliza formato circular.

Forma parte de `Fondo visual y foto juntos`.

---

## 14.1. Estado expandido de escritorio

Área visual aproximada correspondiente a la fotografía:

```text
280px x 280px
```

La fotografía ocupa aproximadamente:

```text
31%
```

del ancho visual de la cabecera.

---

## 14.2. Estado compacto de escritorio

Área visual aproximada correspondiente a la fotografía:

```text
72px x 72px
```

La fotografía permanece visible.

---

## 14.3. Pantallas estrechas

Por debajo de:

```text
1024px
```

la fotografía continúa integrada en `Fondo visual y foto juntos`.

Debe adaptarse proporcionalmente al ancho disponible y a la geometría resultante de la cabecera.

La fotografía permanece presente tanto en el estado expandido como en el compacto y su comportamiento permanece lo mismo al comportamiento del escritorio.

---

## 14.4. Regla visual

No utilizar:

```text
avatar circular aislado
```

La fotografía debe permanecer integrada en `Fondo visual y foto juntos`.

---

# 15. Iconos y controles

## 15.1. Biblioteca de iconos

La iconografía de la interfaz utiliza:

```text
@tabler/icons-angular
```

Los iconos utilizados en la implementación deben corresponder a iconos concretos de esta biblioteca.

La selección del icono pertenece al frontend.

Los datos proporcionados por `sitio-api` no deben contener nombres específicos de Tabler ni decisiones visuales propias de la biblioteca.

Los modelos visuales deben utilizar la misma iconografía definida para la implementación.

Las representaciones que no garanticen el uso de los iconos concretos definidos en esta especificación deben actualizarse antes de ser consideradas referencias finales de iconografía.

---

## 15.2. Mapeo de iconos

La interfaz utiliza un conjunto definido de iconos de `@tabler/icons-angular`.

Cada función visual se relaciona con un icono concreto.

Los nombres definidos a continuación corresponden directamente a los iconos utilizados por la biblioteca.

El mapeo pertenece exclusivamente al frontend.

`Sitio-api` debe proporcionar identificadores o tipos de contenido necesarios para determinar qué debe representarse, pero no determina el nombre del icono de Tabler.

Conceptualmente:

```text
Función, tipo o identificador
        |
        V
Mapeo de sitio
        |
        V
Icono concreto de @tabler/icons-angular
```

No debe seleccionarse un icono alternativo solamente por expresar un concepto parecido.

El icono utilizado debe corresponder al mapeo establecido.

---

## 15.3. Controles globales

| Función                     | Icono concreto    |
| --------------------------- | ----------------- |
| Selector de idioma          | `IconWorld`       |
| Desplegar selector          | `IconChevronDown` |
| Expandir sección            | `IconChevronDown` |
| Contraer sección            | `IconChevronUp`   |
| Activar tema claro          | `IconSun`         |
| Activar tema oscuro         | `IconMoon`        |

El selector de tema representa la acción disponible.

Conceptualmente:

```text
Tema oscuro activo
=> IconSun
=> permite activar tema claro

Tema claro activo
=> IconMoon
=> permite activar tema oscuro
```

---

## 15.4. Navegación principal

| Elemento        | Icono concreto |
| --------------- | -------------- |
| Inicio          | `IconHome`     |
| Sobre mí        | `IconUser`     |
| Contactos       | `IconMail`     |
| Certificaciones | `IconAward`    |
| Proyectos       | `IconFolder`   |
| Artículos       | `IconNotebook` |

El mismo mapeo debe mantenerse en los temas claro y oscuro.

El cambio de tema no sustituye un icono por otro para representar una misma sección.

---

## 15.5. Tipos de contenido y acciones

| Elemento o acción | Icono concreto    |
| ----------------- | ----------------- |
| Proyecto          | `IconFolder`      |
| Artículo          | `IconFileText`    |
| Certificado       | `IconCertificate` |
| Certificación     | `IconAward`       |
| Acceso explícito  | `IconArrowRight`  |

Estos iconos se utilizan cuando el tipo de contenido necesita representación iconográfica, como en el área de Actualizaciones.

El icono de acceso explícito acompaña acciones de navegación hacia otro contenido cuando la composición utiliza una flecha.

---

## 15.6. Sobre mí

Los bloques de `Sobre mí` que utilizan:

```text
type = icon
```

se identifican mediante un `id` estable.

El `id` determina el icono concreto utilizado por el frontend.

El mapeo es:

| Identificador técnico     | Categoría representada      | Icono concreto          |
| ------------------------- | --------------------------- | ----------------------- |
| `technology`              | Tecnología                  | `IconDeviceDesktopCode` |
| `development_automation`  | Desarrollo y automatización | `IconCode`              |
| `professional_experience` | Experiencia profesional     | `IconBriefcase`         |
| `education`               | Formación                   | `IconSchool`            |
| `languages`               | Idiomas                     | `IconLanguage`          |

Conceptualmente:

```text
technology
=> IconDeviceDesktopCode

development_automation
=> IconCode

professional_experience
=> IconBriefcase

education
=> IconSchool

languages
=> IconLanguage
```

El `id` no contiene el nombre de la biblioteca ni del icono.

El icono concreto permanece definido exclusivamente por este mapeo.

Cuando un bloque utiliza:

```text
type = image
```

este mapeo no participa en la representación del elemento visual.

---

## 15.7. Contactos

Cuando un medio de contacto utiliza iconografía, el frontend aplica el icono correspondiente al tipo de medio.

El mapeo definido es:

| Tipo de medio         | Icono concreto      |
| --------------------- | ------------------- |
| Red profesional       | `IconBrandLinkedin` |
| Repositorio de código | `IconBrandGithub`   |
| Sitio web             | `IconWorldWww`      |
| Correo electrónico    | `IconMail`          |
| Teléfono              | `IconPhone`         |
| Mensajería            | `IconBrandWhatsapp` |

Cuando un medio utiliza una imagen en lugar de un icono, este mapeo no participa en la representación del elemento visual.

---

## 15.8. Tamaños

| Uso                   | Tamaño |
| --------------------- | -----: |
| Navegación principal  | `22px` |
| Idioma                | `20px` |
| Tema                  | `20px` |
| Tarjetas / destacados | `18px` |

Los iconos funcionan como apoyo visual.

No sustituyen el texto cuando el significado pueda resultar ambiguo.

Los tamaños definidos no modifican el icono seleccionado por el mapeo.

---

## 15.9. Selector de idioma

En escritorio:

```text
altura             => 48px
ancho              => 104px
padding horizontal => 12px
border-radius      => 0
borde              => 1px
```

Debe permanecer directamente visible.

No debe estar oculto dentro de una sección de configuración.

En pantallas estrechas continúa directamente disponible dentro de:

```text
Menú | Idioma | Tema
```

No se traslada al interior de `Menú`.

---

## 15.10. Selector de tema

En escritorio:

```text
altura        => 48px
ancho         => 48px
border-radius => 0
borde         => 1px
```

Se ubica inmediatamente junto al selector de idioma.

En pantallas estrechas continúa directamente disponible dentro de:

```text
Menú | Idioma | Tema
```

Debe permitir cambiar directamente entre:

```text
tema claro
tema oscuro
```

El cambio de tema no modifica la página representada.

Debe conservar:

```text
Contenido
Selección editorial
Cantidad de elementos
Orden
Jerarquía
Navegación
Dimensiones correspondientes a la composición activa
Espaciado
Disposición correspondiente a la composición activa
Formato de las tarjetas
Actualizaciones
Iconos
```

Solamente cambia la representación visual correspondiente al tema seleccionado.

---

## 15.11. Botón principal

Base:

```text
altura             => 48px
padding horizontal => 24px
font-size          => 16px
font-weight        => 600
border-radius      => 0
```

En escritorio utiliza su ancho natural cuando no existe una regla específica diferente.

En pantallas estrechas, las acciones principales que forman parte del flujo de contenido deben ocupar:

```text
ancho => 100%
```

cuando corresponde a la composición definida.

La altura permanece en:

```text
48px
```

---

## 15.12. Botón secundario

Base:

```text
altura             => 48px
padding horizontal => 24px
borde              => 1px
border-radius      => 0
```

Las reglas responsive de ancho siguen la composición de la acción correspondiente.

---

# 16. Inicio

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

## 16.1. Estructura general

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

## 16.2. Secciones destacadas

Las secciones destacadas presentan contenido seleccionado editorialmente.

La composición no depende de una cantidad fija de elementos.

Los componentes deben admitir variaciones en la cantidad recibida sin modificar la estructura general de Inicio.

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

Las tarjetas de contenido destacado utilizan la misma regla de rejilla adaptable establecida en `20.3. Rejilla`.

---

## 16.3. Proyecto destacado

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

## 16.4. Artículo destacado

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

## 16.5. elemento destacado de Certificaciones

La sección debe representar:

```text
Certificado
Certificación
```

Cada elemento presenta la información resumida necesaria para reconocer el elemento y acceder a su página individual.

La tarjeta completa no constituye implícitamente un enlace.

---

## 16.6. Coherencia entre destacados

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

El cambio de tema no modifica la estructura interna, el orden, el contenido ni la disposición correspondiente al ancho disponible.

---

## 16.7. Área de exposición

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

Debe admitir variaciones en la cantidad disponible sin modificar la estructura general del área.

No deben añadirse dentro de esta región citas, frases de efecto ni otros bloques que no representen una actualización.

---

## 16.8. Actualización

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

El icono debe corresponder al mapeo definido en `15.5. Tipos de contenido y acciones`.

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

---

## 16.9. Relación entre contenido principal y exposición

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

## 16.10. Inicio en escritorio intermedio

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

## 16.11. Inicio en pantallas estrechas

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

Las rejillas internas continúan presentando tantas tarjetas completas como permita el ancho disponible.

---

# 17. Páginas internas

Las páginas internas comparten un mismo armazón.

En escritorio:

```text
+-------------+----------------------------------------+
|             |              CABECERA                  |
|             |                                        |
|             | Fondo visual y foto juntos +           |
|             | nombre + descripción breve             |
|             +----------------------------------------+
|             |                                        |
|             |                                        |
| NAVEGACIÓN  |              CONTENIDO                 |
|             |                                        |
| Idioma      |                                        |
| Tema        |                                        |
|             |                                        |
| Inicio      |                                        |
| Sobre mí    |                                        |
| Contactos   |                                        |
| Certific.   |                                        |
| Proyectos   |                                        |
| Artículos   |                                        |
|             |                                        |
+-------------+----------------------------------------+
```

Este modelo se aplica a:

```text
Sobre mí
Contactos
Certificaciones
Certificado
Certificación
Proyectos
Proyecto
Artículos
Artículo
```

Y sus derivaciones.

---

## 17.1. Región Contenido

La región `Contenido` constituye el espacio variable de las páginas internas.

No implica una composición textual única.

debe contener:

```text
Texto
Imágenes
Iconos
Tarjetas
Rejillas
Formularios
Metadatos
Contenido estructurado
Contenido proveniente de Markdown
```

según la página correspondiente.

La variación ocurre dentro de esta región sin modificar:

```text
Cabecera
Navegación
Estructura global correspondiente al ancho disponible
Idioma activo
Tema activo
```

---

## 17.2. Listado y detalle

Las secciones que agrupan múltiples elementos utilizan la misma región `Contenido` para su listado y para el elemento individual.

Conceptualmente:

```text
Listado
|
+-- región Contenido
    +-- todos los elementos de la categoría
```

Al seleccionar un elemento:

```text
Detalle
|
+-- región Contenido
    +-- contenido del elemento seleccionado
```

No aparece una nueva región global ni una estructura paralela para el detalle.

---

## 17.3. Pantallas estrechas

Cuando:

```text
ancho < 1024px
```

las páginas internas utilizan:

```text
Cabecera
Navegación móvil
Contenido
```

como armazón global.

La región `Contenido` utiliza el ancho disponible.

La composición global de una columna no obliga a convertir todos los componentes internos en una única columna.

La regla interna es:

```text
Composición horizontal que cabe correctamente
=> debe mantenerse

Composición horizontal que deja de caber correctamente
=> reorganizar verticalmente
```

La decisión depende del espacio real disponible y de la legibilidad del componente.

---

## 17.4. Contenido interno ancho

La página completa no debe adquirir desplazamiento horizontal debido a un componente interno.

Cuando un componente supera el espacio disponible, la prioridad es:

```text
1. Reorganizar
2. Redimensionar proporcionalmente
3. Adaptar internamente
4. Utilizar desplazamiento horizontal solamente en el elemento
```

La reorganización se utiliza cuando debe cambiarse la disposición sin perder información o significado.

El redimensionamiento se utiliza para elementos que continúan siendo legibles después de reducirse.

La adaptación interna debe modificar la representación del componente.

Ejemplos:

```text
Metadatos horizontales
=> disposición vertical
```

```text
Tabla
=> representación adaptada mediante bloques
```

cuando esa transformación conserva correctamente la información.

El desplazamiento horizontal se utiliza solamente cuando las alternativas anteriores perjudicarían el contenido.

Cuando sea necesario:

```text
Elemento concreto
=> overflow horizontal
```

No:

```text
Página completa
=> overflow horizontal
```

---

# 18. Sobre mí

`Sobre mí` combina contenido textual con elementos visuales relacionados directamente con aquello que se está comunicando.

La página no debe convertirse en una sucesión extensa de texto sin pausas visuales.

---

## 18.1. Estructura

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

## 18.2. Relación entre texto y elemento visual

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

## 18.3. Bloque con icono

Cuando el contenido establece que el elemento visual es un icono:

```text
type = icon
```

`Sitio` selecciona el icono concreto correspondiente mediante el identificador del bloque.

Los identificadores y sus iconos se encuentran definidos en `15.6. Sobre mí`.

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

## 18.4. Bloque con imagen

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

`alt` proporciona su alternativa textual.

`href` determina el destino asociado.

---

## 18.5. Adaptación responsive

En escritorio debe mantenerse la composición horizontal definida editorialmente entre texto y elemento visual.

Cuando:

```text
ancho < 1024px
```

los bloques que no deben conservar correctamente esa composición se reorganizan verticalmente.

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

# 19. Contactos

La página de Contactos combina:

```text
Medios de contacto
Formulario de contacto
```

dentro de la misma región `Contenido`.

---

## 19.1. Medios de contacto

Los medios de contacto utilizan tarjetas compatibles con el lenguaje visual general del sitio.

Conceptualmente:

```text
--------------------------------
| icono o imagen               |
| ---------------------------- |
| nombre del medio             |
| enlace del medio             |
--------------------------------
```

La tarjeta contiene:

```text
elemento visual
Tipo de medio
Enlace
```

Cuando el elemento visual es un icono, debe utilizarse el mapeo definido en `15.7. Contactos`.

El propio enlace del medio es un vínculo que lleva hacia el medio directamente.

---

## 19.2. Rejilla de contactos

Las tarjetas se organizan horizontalmente mientras exista espacio disponible.

La cantidad de columnas depende del ancho disponible.

Cuando una nueva tarjeta ya no cabe correctamente en la fila actual, continúa en la siguiente.

Los medios presentes dependen de los datos disponibles.

No se define un número fijo de tarjetas por fila.

---

## 19.3. Formulario

El formulario aparece después de los medios de contacto.

Contiene:

```text
Nombre
Apellido
Dirección de correo electrónico
Motivo del contacto
Mensaje
```

Conceptualmente:

```text
--------------------------------------
| Nombre                             |
| ---------------------------------- |
| |                                | |
| ---------------------------------- |
|                                    |
| Apellido                           |
| ---------------------------------- |
| |                                | |
| ---------------------------------- |
|                                    |
| Dirección de correo electrónico    |
| ---------------------------------- |
| |                                | |
| ---------------------------------- |
|                                    |
| Motivo del contacto                |
| ---------------------------------- |
| |                                | |
| ---------------------------------- |
|                                    |
| Mensaje                            |
| ---------------------------------- |
| |                                | |
| |                                | |
| |                                | |
| |                                | |
| ---------------------------------- |
|                                    |
| Enviar                             |
--------------------------------------
```

Todos los campos son obligatorios.

`Mensaje` utiliza un campo de varias líneas.

`Motivo del contacto` utiliza un campo de una línea.

El control de envío utiliza el tratamiento definido para los botones principales.

Conceptualmente:

```text
first_name
=> 1..100 caracteres

last_name
=> 1..100 caracteres

email
=> dirección válida
=> máximo 254 caracteres

subject
=> 1..200 caracteres

message
=> 1..10000 caracteres
```

---

## 19.4. Integración visual

El formulario no debe parecer un elemento perteneciente a otro sistema.

Debe utilizar:

```text
tipografía del sitio
bordes del sitio
superficies del tema activo
colores interactivos
espaciado base
foco visible
botón principal
```

Los mecanismos técnicos de validación, envío y protección no modifican la identidad visual general de la página.

---

## 19.5. Adaptación responsive

Los campos permanecen verticales y utilizan todo el ancho disponible de la región del formulario.

No se reorganizan horizontalmente en escritorio.

El botón principal utiliza:

```text
ancho >= 1024px
=> ancho natural
=> altura 48px
=> padding horizontal 24px
```

Cuando:

```text
ancho < 1024px
```

utiliza:

```text
ancho  => 100%
altura => 48px
```

La misma regla se aplica durante:

```text
Enviando...
```

La adaptación no modifica los estados ni el contenido del formulario.

---

# 20. Tarjetas

Las tarjetas constituyen un patrón visual compartido por diferentes regiones del sitio.

Compartir el patrón no implica compartir un único contrato de datos.

---

## 20.1. Estructura común

Conceptualmente:

```text
------------------------------------
| zona visual                      |
| -------------------------------- |
| contenido específico             |
| del tipo de elemento             |
|                                  |
| acción o enlace, si corresponde  |
------------------------------------
```

El lenguaje común comprende:

```text
tratamiento de superficie
borde
ausencia de redondeo por defecto
tipografía
espaciado
jerarquía
tratamiento de imagen o icono
tratamiento de enlaces
comportamiento entre temas
```

---

## 20.2. Contenido específico

Cada tipo de tarjeta conserva sus propios campos.

No deben añadirse propiedades únicamente con el objetivo de hacer que dos tipos diferentes tengan el mismo contenido interno.

Conceptualmente:

```text
Contacto
=> icono o imagen
=> tipo de medio
=> enlace

Proyecto
=> imagen
=> nombre
=> descripción
=> Ver proyecto

Artículo
=> imagen
=> título
=> descripción
=> fecha de publicación
=> fecha de actualización
=> Leer artículo

Certificado
=> imagen
=> tipo
=> nombre
=> entidad
=> fecha
=> Ver certificado

Certificación
=> imagen
=> tipo
=> nombre
=> entidad
=> fecha
=> expiración
=> Ver certificación
```

---

## 20.3. Rejilla

Las páginas de listado y las regiones destacadas que utilizan tarjetas presentan tantas tarjetas completas como permita el ancho disponible.

No se define:

```text
cantidad mínima fija de columnas
cantidad máxima fija de columnas
cantidad fijas de tarjetas por fila
```

La regla es:

```text
Tarjetas que caben correctamente
=> permanecen en la fila actual

Siguiente tarjeta ya no cabe correctamente
=> continúa en la fila siguiente
```

La cantidad de columnas constituye una consecuencia del espacio disponible.

El mínimo natural es una tarjeta por fila.

Conceptualmente:

```text
Si cabe uno
=> una tarjeta por fila

Si cabe más que uno
=> cuanto cabe de tarjeta por fila sin romper la tarjeta como elemento único
```

La cantidad total de elementos no constituye una restricción estructural del componente.

Esta regla se aplica a las rejillas de:

```text
Proyectos
Artículos
Certificaciones
Contactos
Contenido destacado
```

---

## 20.4. Altura y alineación

Las tarjetas pertenecientes a una misma rejilla deben mantener una composición visual coherente.

La estructura interna debe permitir que diferencias razonables de longitud de texto no destruyan la alineación general.

Cuando existe una acción explícita al final de la tarjeta, su posición debe permanecer visualmente consistente dentro de la rejilla.

---

## 20.5. Interacción

La tarjeta completa nunca debe convertirse implícitamente en enlace, siempre habrá un enlace específico para la acción explícita.

En Contactos, el propio valor del medio constituye el enlace y no se añade una segunda acción redundante.

---

# 21. Certificaciones

La sección visible continúa denominándose:

```text
Certificaciones
```

y agrupa dos tipos de elementos:

```text
Certificado
Certificación
```

Los dos tipos pertenecen a la misma sección pero se identifican explícitamente.

---

## 21.1. Listado

El listado utiliza la rejilla general de tarjetas.

Cada elemento incluye una indicación visible de su tipo.

---

## 21.2. Certificado

Una tarjeta de certificado utiliza:

```text
------------------------------------
| imagen                           |
| -------------------------------- |
| Certificado                      |
| Nombre                           |
| Entidad                          |
| Fecha                            |
| Ver certificado                  |
------------------------------------
```

`Certificado` identifica visualmente el tipo de elemento.

No dispone de una línea artificial de expiración.

---

## 21.3. Certificación

Una tarjeta de certificación utiliza:

```text
------------------------------------
| imagen                           |
| -------------------------------- |
| Certificación                    |
| Nombre                           |
| Entidad                          |
| Fecha                            |
| Expiración                       |
| Ver certificación                |
------------------------------------
```

`Certificación` identifica visualmente el tipo de elemento.

La línea de expiración forma parte de la estructura de esta tarjeta.

Cuando la certificación no expira, debe permanecer la línea y utilizar una representación localizada equivalente a:

```text
Expiración: No expira
```

No debe representarse:

```text
null
```

ni dejar un hueco sin contenido.

---

## 21.4. Diferencia gráfica entre tipos

Certificado y Certificación deben presentar diferencias internas porque representan elementos distintos.

Esta diferencia no rompe la identidad visual general.

Ambos conservan:

```text
misma familia de tarjeta
misma geometría general
mismo tratamiento de imagen
mismos bordes
misma tipografía
mismo sistema de espaciado
misma jerarquía general
mismo comportamiento entre temas
```

El tipo visible permite reconocer la diferencia sin depender de la existencia o ausencia de determinados campos.

---

## 21.5. Detalle

Al seleccionar un elemento, la región `Contenido` completa representa el elemento.

El detalle de un certificado presenta los datos correspondientes a su propio tipo.

El detalle de una certificación presenta además la información propia de la credencial.

Cuando una certificación no dispone de código o enlace de verificación, el espacio correspondiente utiliza un texto localizado equivalente a:

```text
No disponible
```

No se muestra `null` como contenido visible.

El detalle no incorpora una sección adicional de conocimientos relacionados.

---

## 21.6. Adaptación responsive del detalle

En escritorio debe mantenerse una composición horizontal mientras el espacio disponible permita representar correctamente sus regiones.

Cuando:

```text
ancho < 1024px
```

el detalle se reorganiza verticalmente.

Para una certificación, el orden conceptual es:

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

Cada bloque utiliza el ancho disponible.

La imagen se redimensiona proporcionalmente.

Los valores definidos por el contrato se conservan.

En particular:

```text
Sin fecha de expiración
=> No expira

Credencial no disponible
=> No disponible
```

Un certificado utiliza la misma lógica responsive, pero no incorpora campos propios de una certificación que no pertenezcan a su tipo.

---

# 22. Proyectos

La página de Proyectos utiliza la rejilla general de tarjetas.

---

## 22.1. Tarjeta

Cada tarjeta presenta:

```text
------------------------------------
| imagen                           |
| -------------------------------- |
| Nombre                           |
| Descripción breve                |
| Ver proyecto                     |
------------------------------------
```

La tarjeta funciona como representación resumida y como invitación a acceder al detalle.

No muestra:

```text
Lenguajes
Datos completos del repositorio
```

Estos datos pertenecen al detalle.

---

## 22.2. Detalle

Al seleccionar `Ver proyecto`, la región `Contenido` completa representa el proyecto.

El detalle debe presentar:

```text
Nombre
Tipo
Descripción breve
Imagen
Lenguaje principal
Última actualización
Descripción
Acceso al repositorio
Volver a proyectos
```

La información principal se organiza mediante la imagen del proyecto y un panel de metadatos.

El panel de metadatos presenta:

```text
Tipo
Lenguaje principal
Última actualización
```

No debe incorporar un campo denominado:

```text
Enfoque
```

El repositorio no se presenta como una línea de metadatos denominada:

```text
Repositorio
```

Cuando existe un repositorio accesible, se representa mediante una acción explícita equivalente a:

```text
Ver en GitHub
```

El regreso al listado utiliza una acción explícita equivalente a:

```text
Volver a proyectos
```

---

## 22.3. Lenguaje principal

El detalle representa el lenguaje principal del proyecto como información técnica.

Conceptualmente:

```text
Lenguaje principal
=> lenguaje
```

No se requiere representar en el detalle una distribución porcentual de todos los lenguajes del repositorio.

---

## 22.4. Orden del listado

El orden visual del listado constituye una decisión editorial.

No debe modificarse automáticamente solamente porque un repositorio haya recibido una actualización técnica reciente.

---

## 22.5. Adaptación responsive del detalle

En escritorio debe mantenerse la composición horizontal entre imagen y panel de metadatos cuando el espacio disponible resulta adecuado.

Cuando:

```text
ancho < 1024px
```

la imagen y el panel de metadatos se reorganizan verticalmente.

Cada región utiliza el ancho disponible.

La imagen mantiene sus proporciones.

El panel de metadatos debe reorganizar también sus elementos internamente en disposición vertical cuando sea necesario.

La adaptación conserva:

```text
Contenido
Orden semántico
Acciones
Información técnica
```

No elimina datos para mantener la composición horizontal de escritorio.

---

# 23. Artículos

La página de Artículos utiliza la rejilla general de tarjetas.

---

## 23.1. Tarjeta

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

## 23.2. Fecha de publicación y actualización

La fecha de publicación corresponde a la publicación inicial.

La fecha de actualización corresponde a la última versión publicada.

Cuando todavía no existe una modificación posterior:

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

## 23.3. Artículo

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

---

## 23.4. Lectura

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

---

## 23.5. Adaptación responsive del artículo

Cuando:

```text
ancho < 1024px
```

el artículo utiliza el ancho disponible dentro del contenedor y respeta:

```text
padding horizontal general => 16px
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

Las imágenes y demás elementos visuales se redimensionan proporcionalmente cuando continúan siendo legibles.

Para contenidos anchos se utiliza la prioridad:

```text
1. Reorganizar
2. Redimensionar proporcionalmente
3. Adaptar internamente
4. Desplazamiento horizontal propio
```

La página completa no adquiere desplazamiento horizontal por la presencia de una tabla, bloque de código, diagrama u otro elemento.

---

# 24. Estados comunes

Los estados de la aplicación forman parte de la misma composición visual utilizada por el contenido normal.

No constituyen páginas, modales ni sistemas visuales independientes.

La representación de un estado debe conservar, siempre que las regiones correspondientes continúen disponibles:

```text
Cabecera
Navegación
Idioma activo
Tema activo
Estructura de la página
Identidad visual
```

Los mensajes visibles de estado pertenecen a los elementos localizados de la interfaz.

Los errores técnicos internos no se presentan directamente.

No deben mostrarse al usuario:

```text
Excepciones
Trazas
Detalles internos del backend
Mensajes técnicos sin localizar
Códigos HTTP como contenido principal
```

cuando esa información no modifica la acción que debe realizar.

---

## 24.1. Unidad de presentación

Los estados se aplican a unidades de presentación.

Una unidad de presentación constituye la menor entidad que debe comprenderse y utilizarse de forma independiente.

Una unidad solamente se presenta como contenido normal cuando todos sus elementos necesarios se encuentran disponibles.

Conceptualmente:

```text
Unidad completa
=> presentar contenido

Unidad incompleta
=> no presentar parcialmente
=> representar el estado correspondiente
```

La cantidad de solicitudes HTTP utilizadas para obtener una unidad no determina sus límites visuales.

La unidad se define por la estructura y el significado de aquello que se representa.

### Colecciones

En una colección, cada elemento independiente constituye su propia unidad.

Esto se aplica, entre otros, a:

```text
Tarjeta de proyecto
Tarjeta de artículo
Tarjeta de certificado
Tarjeta de certificación
Elemento destacado
Actualización
```

Por lo tanto, una colección debe presentar simultáneamente unidades que ya se encuentran completas y posiciones que todavía se encuentran cargando o que terminaron con error.

Conceptualmente:

```text
Rejilla
|
+-- unidad completa
|   => contenido
|
+-- unidad completa
|   => contenido
|
+-- unidad fallida
|   => aviso de error
|
+-- unidad completa
    => contenido
```

Una falla en una unidad no invalida las demás unidades completas de la misma colección.

Cuando la posición de una unidad fallida es conocida, el aviso de error conserva esa posición dentro de la colección.

El estado de error no debe adoptar la apariencia de una tarjeta válida ni presentar contenido incompleto como si fuera el elemento final.

### Unidades únicas

Cuando la región representada constituye un contenido indivisible, toda la región constituye una sola unidad.

Se consideran unidades únicas:

```text
Cabecera
Sobre mí
Detalle de proyecto
Detalle de artículo
Detalle de certificado
Detalle de certificación
Contactos durante su carga
```

Si una parte necesaria de una unidad única no debe obtenerse o representarse correctamente, no se presenta el resto como un contenido completo.

La unidad adopta el estado correspondiente.

---

## 24.2. Carga

El estado de carga utiliza skeleton.

No se utiliza:

```text
Cargando...
```

como sustitución general del contenido.

Tampoco se utiliza un spinner global para sustituir la página.

Las regiones estructurales disponibles permanecen visibles y utilizables durante la carga.

Conceptualmente:

```text
Cabecera disponible
=> permanece

Navegación disponible
=> permanece

Contenido pendiente
=> skeleton
```

El skeleton debe aproximarse a la geometría del contenido que sustituirá.

No debe utilizar una forma única para todos los tipos de contenido.

Ejemplos:

```text
Tarjeta pendiente
=> zona visual
=> líneas correspondientes al texto
=> espacio correspondiente a la acción

Detalle pendiente
=> bloques equivalentes a título, imagen, metadatos y contenido

Navegación subordinada pendiente
=> líneas equivalentes a los accesos que aparecerán
```

El skeleton utiliza superficies neutrales derivadas del tema activo.

No se utiliza colores principales para la animación. El estado incorpora una franja de luminosidad en gradiente que se desplaza horizontalmente desde la izquierda hacia la derecha.

Conceptualmente:

```text
base neutral
        |
        V
franja de luminosidad
        |
        V
desplazamiento horizontal
```

El skeleton solamente existe mientras una operación se encuentra realmente pendiente.

Cuando la operación termina:

```text
éxito
=> contenido

vacío
=> estado vacío

error
=> estado de error
```

Un error definitivo no mantiene skeleton.

### Colecciones durante la carga

Las unidades completas deben presentarse a medida que se encuentran disponibles.

Una unidad individual todavía incompleta permanece representada mediante su skeleton.

No se muestra parcialmente.

Conceptualmente:

```text
Elemento 1 completo
=> contenido

Elemento 2 pendiente
=> skeleton

Elemento 3 completo
=> contenido
```

---

## 24.3. Contenido vacío

El estado vacío solamente debe aparecer después de completar correctamente la carga.

Conceptualmente:

```text
Solicitud pendiente
=> skeleton

Solicitud correcta con elementos
=> contenido

Solicitud correcta sin elementos
=> estado vacío

Solicitud fallida
=> error
```

Un estado vacío no constituye un error.

No utiliza:

```text
color semántico de error
imagen genérica
ilustración decorativa obligatoria
skeleton detenido
tarjeta ficticia
```

El texto utiliza la tipografía normal de interfaz y el tratamiento de texto secundario del tema activo.

En una rejilla, el mensaje ocupa la región disponible del listado.

No se representa como si fuera la primera tarjeta de una colección inexistente.

### Proyectos

Cuando el listado no contiene proyectos publicados:

```text
No hay proyectos publicados.
```

### Artículos

Cuando el listado no contiene artículos publicados:

```text
No hay artículos publicados.
```

### Certificaciones

Cuando el listado no contiene certificados ni certificaciones publicados:

```text
No hay certificaciones publicadas.
```

### Inicio

Las secciones destacadas disponen de estados vacíos independientes.

```text
Proyectos destacados
=> No hay proyectos destacados.

Artículos destacados
=> No hay artículos destacados.

Certificaciones destacadas
=> No hay certificaciones destacadas.
```

El acceso al listado completo permanece disponible.

Ejemplo:

```text
Proyectos destacados

No hay proyectos destacados.

Ver todos los proyectos
```

La ausencia de contenido destacado no implica que el listado completo de esa categoría se encuentre vacío.

### Actualizaciones

Cuando no existen actualizaciones que representar:

```text
No hay actualizaciones recientes.
```

### Sobre mí

Cuando la carga termina correctamente y no existe información publicada:

```text
No hay información publicada en esta sección.
```

Si el contenido debería existir pero se encuentra incompleto o inválido, se utiliza el estado de error y no el estado vacío.

### Contactos

Cuando la consulta de medios de contacto termina correctamente sin medios publicados:

```text
Medios de contacto

No hay medios de contacto publicados.

Formulario de contacto

[ formulario ]
```

La ausencia de medios de contacto no elimina el formulario.

### elementos individuales

Un elemento individual no utiliza estado vacío para sustituir datos obligatorios.

Conceptualmente:

```text
elemento existente y completo
=> contenido

elemento existente pero incompleto
=> error

elemento inexistente
=> no encontrado
```

Los campos opcionales mantienen las reglas específicas de su contrato.

Ejemplos:

```text
Certificación sin expiración
=> No expira

Credencial no disponible
=> No disponible
```

No constituyen estados vacíos.

---

## 24.4. Error de carga

Los errores de carga utilizan el color semántico de error correspondiente al tema activo.

La representación continúa utilizando:

```text
tipografía del sitio
espaciado del sitio
superficies del tema activo
bordes del sitio
```

No se introduce una pantalla de error visualmente independiente.

La unidad que falla deja de representar skeleton.

No se muestran fragmentos de una unidad incompleta como si el contenido hubiera cargado correctamente.

### Colecciones

Cuando una unidad independiente falla dentro de una colección, las demás unidades completas permanecen visibles.

La posición correspondiente a la unidad fallida presenta el aviso.

Ejemplo para un proyecto:

```text
No fue posible cargar este proyecto.

Actualice la página para volver a intentarlo.
```

Ejemplo para un artículo:

```text
No fue posible cargar este artículo.

Actualice la página para volver a intentarlo.
```

Para certificados y certificaciones se utiliza la misma estructura adaptada al tipo correspondiente.

La región de error ocupa aproximadamente el espacio que corresponde a la unidad dentro de la rejilla, sin imitar una tarjeta válida.

### Unidades únicas

Cuando falla una unidad única de la región `Contenido`, esa región se sustituye por un aviso equivalente a:

```text
No fue posible cargar la información de esta página.

Actualice la página para volver a intentarlo.
```

En Contactos se utiliza:

```text
No fue posible cargar la información de contacto.

Actualice la página para volver a intentarlo.
```

El nuevo intento ocurre mediante una nueva carga realizada por el usuario.

### elementos visuales obligatorios

Una imagen u otro elemento visual necesario forma parte de la unidad a la que pertenece.

Si el elemento visual obligatorio falla, la unidad se considera incompleta.

Conceptualmente:

```text
Imagen obligatoria cargada
+ datos obligatorios cargados
=> unidad completa

Imagen obligatoria fallida
=> unidad incompleta
=> error
```

No se utiliza una imagen genérica de sustitución para transformar una unidad incompleta en una representación aparentemente válida.

Un elemento visual puramente opcional o decorativo debe seguir sus propias reglas cuando su ausencia no invalida el contenido.

---

## 24.5. Estados de la navegación

La estructura principal de navegación permanece disponible aunque falle la obtención de elementos subordinados.

Continúan disponibles:

```text
Inicio
Sobre mí
Contactos
Certificaciones
Proyectos
Artículos
Controles globales
```

cuando esos elementos no dependen de la operación que falló.

### Carga de elementos subordinados

Cuando una sección se encuentra expandida y sus elementos subordinados todavía están pendientes, el área de subelementos utiliza skeleton.

Ejemplo:

```text
Proyectos
    [ skeleton ]
    [ skeleton ]
    [ skeleton ]
```

El skeleton mantiene la geometría aproximada de un acceso subordinado.

No representa tarjetas dentro de la navegación.

Cuando una sección se encuentra contraída, no es necesario representar visualmente la carga de elementos que no se encuentran visibles.

Las secciones independientes deben alcanzar estados diferentes.

Conceptualmente:

```text
Certificaciones
=> cargado

Proyectos
=> cargando

Artículos
=> cargado
```

### Error de elementos subordinados

Si falla la obtención de los elementos subordinados, la sección principal continúa disponible.

El acceso al listado completo también permanece disponible.

Ejemplo:

```text
Proyectos

No fue posible cargar los proyectos.

Ver todos los proyectos
```

Para las demás secciones se utiliza el texto correspondiente:

```text
No fue posible cargar los artículos.

No fue posible cargar las certificaciones.
```

No se incorpora dentro de la navegación:

```text
Actualice la página para volver a intentarlo.
```

La navegación debe mantener una representación compacta.

### Sección sin elementos subordinados

Cuando una sección se carga correctamente y no contiene elementos subordinados:

```text
Proyectos
```

permanece como acceso a su listado.

No se incorpora dentro de la navegación:

```text
No hay proyectos publicados.
```

La información de estado vacío pertenece a la región de contenido de la página correspondiente.

---

## 24.6. Estados de la cabecera

La cabecera constituye una unidad única.

Durante su carga mantiene el espacio estructural correspondiente y utiliza skeleton adaptado a su composición.

### Cabecera expandida pendiente en escritorio

El skeleton respeta aproximadamente:

```text
altura             => 320px
Fondo visual y foto juntos
Nombre
Descripción breve
```

### Cabecera compacta pendiente en escritorio

Cuando corresponde la geometría compacta, respeta aproximadamente:

```text
altura             => 112px
Fondo visual y foto juntos
Nombre
```

### Pantallas estrechas

Cuando:

```text
ancho < 1024px
```

el skeleton no utiliza obligatoriamente las alturas de escritorio.

Respeta aproximadamente la geometría responsive resultante del contenido, el padding y el ancho disponible.

En estado expandido representa:

```text
Fondo visual y foto juntos
Nombre
Descripción breve
```

En estado compacto representa:

```text
Fondo visual y foto juntos
Nombre
```

La cabecera no se presenta parcialmente.

Si una parte obligatoria todavía se encuentra pendiente, la unidad continúa en estado de carga.

### Error

Cuando la cabecera no debe constituirse completamente:

```text
No fue posible cargar la información de la cabecera.

Actualice la página para volver a intentarlo.
```

La región de cabecera presenta el aviso dentro del espacio correspondiente.

Una falla de la cabecera no elimina la navegación ni invalida las regiones de contenido que puedan continuar funcionando.

---

## 24.7. Contenido no encontrado

El estado no encontrado se utiliza cuando la aplicación determina que la dirección o el elemento solicitado no existe.

No se utiliza como sustitución de un error de comunicación o de carga.

La estructura global del sitio permanece visible cuando se encuentra disponible.

No es necesario presentar:

```text
404
```

como elemento visual principal.

### Página desconocida

Una dirección que no corresponde a una página conocida utiliza:

```text
Página no encontrada

La página que buscas no existe o ya no está disponible.

Volver al inicio
```

`Volver al inicio` constituye una acción normal de navegación.

### Proyecto

```text
Proyecto no encontrado

El proyecto que buscas no existe o ya no está disponible.

Ver todos los proyectos
```

### Artículo

```text
Artículo no encontrado

El artículo que buscas no existe o ya no está disponible.

Ver todos los artículos
```

### Certificado

```text
Certificado no encontrado

El certificado que buscas no existe o ya no está disponible.

Ver todas las certificaciones
```

### Certificación

```text
Certificación no encontrada

La certificación que buscas no existe o ya no está disponible.

Ver todas las certificaciones
```

Los estados no encontrados no incorporan una indicación de actualizar la página.

---

## 24.8. Estados del formulario de contacto

Los estados del formulario se representan dentro de la propia página de Contactos.

No sustituyen la navegación ni las demás regiones del sitio.

Los valores introducidos se conservan siempre que el resultado de la operación permita o requiera una nueva tentativa.

---

### 24.8.1. Estado normal

El control presenta:

```text
Enviar
```

Los campos permanecen disponibles para edición.

---

### 24.8.2. Envío en curso

Después de activar `Enviar`, el formulario permanece visible.

Los valores introducidos permanecen presentes.

Durante la operación:

```text
Campos
=> conservan valores
=> temporalmente no modificables

Botón
=> Enviando...
=> no permite iniciar un segundo envío simultáneo
```

No se utiliza:

```text
skeleton
overlay de página completa
spinner global
```

para representar esta operación.

La navegación permanece disponible.

Cuando la operación termina, el control vuelve a:

```text
Enviar
```

independientemente del resultado recibido.

El frontend no conserva una condición local que impida futuros intentos basándose en una respuesta anterior del backend.

El ancho del botón durante el envío conserva las reglas responsive definidas para el estado normal.

---

### 24.8.3. Envío satisfactorio

Cuando la interfaz recibe el resultado correspondiente a una solicitud aceptada:

```text
Mensaje enviado correctamente.
```

El mensaje utiliza el color semántico de éxito del tema activo.

Después del resultado satisfactorio:

```text
Campos
=> vacíos
=> disponibles

Botón
=> Enviar
```

No se añade una segunda frase de confirmación.

No se incorpora:

```text
Aceptar
Cerrar
Enviar otro
```

como acción adicional.

El formulario permanece en la página y debe volver a utilizarse.

---

### 24.8.4. Validación

Los errores de validación se representan junto al campo correspondiente.

Los valores introducidos permanecen en el formulario.

El campo afectado utiliza el tratamiento de error definido por la identidad visual.

El mensaje debe indicar la condición concreta que necesita corrección.

Ejemplos:

```text
Este campo es obligatorio.
```

```text
Introduzca una dirección de correo electrónico válida.
```

```text
El nombre no debe superar los 100 caracteres.
```

```text
El apellido no debe superar los 100 caracteres.
```

```text
El motivo no debe superar los 200 caracteres.
```

```text
El mensaje no debe superar los 10000 caracteres.
```

La validación no depende únicamente de un mensaje general equivalente a:

```text
El formulario contiene errores.
```

El usuario debe poder identificar qué campo requiere modificación.

Cuando la validación del frontend determina que los datos todavía no cumplen el contrato, no se realiza la solicitud.

Una validación equivalente informada por el backend utiliza la misma representación visible cuando corresponde a un campo concreto.

Después de corregir los valores:

```text
Enviar
```

permanece disponible para una nueva tentativa.

---

### 24.8.5. Honeypot

El honeypot forma parte de la protección del formulario pero no introduce una interacción visible adicional.

Su implementación concreta no forma parte de esta especificación visual.

Cuando el mecanismo se activa, no se presenta un estado específico que permita distinguir visualmente ese caso de una solicitud aceptada.

Conceptualmente:

```text
Solicitud aceptada para la interfaz
=> Mensaje enviado correctamente.

Honeypot activado
=> misma representación visible
```

La activación del mecanismo no debe revelar visualmente qué condición interna fue detectada.

---

### 24.8.6. Límite de envíos

El límite definido para el formulario es:

```text
5 envíos por IP por hora
```

Cuando el backend informa que el límite se encuentra activo, el formulario conserva los valores introducidos.

El aviso utiliza el color semántico de advertencia del tema activo.

Texto:

```text
Se alcanzó el límite de 5 envíos por hora.

Inténtelo de nuevo más tarde.
```

Después de la respuesta:

```text
Botón
=> Enviar
```

permanece disponible.

El frontend no mantiene:

```text
contador de envíos
temporizador
cuenta regresiva
bloqueo local permanente del botón
estado local equivalente al límite del backend
```

Cada nueva activación de `Enviar` genera una nueva solicitud.

Corresponde al backend determinar en ese momento si la solicitud debe continuar o si el límite sigue vigente.

---

### 24.8.7. Fallo de envío

Cuando los datos son válidos pero la operación no debe completarse:

```text
No fue posible enviar el mensaje.

Inténtelo de nuevo.
```

El aviso utiliza el color semántico de error del tema activo.

Los valores introducidos permanecen en el formulario.

Conceptualmente:

```text
Campos
=> conservan valores
=> disponibles nuevamente

Botón
=> Enviar
```

No se vacían los campos.

No se actualiza automáticamente la página.

No se sustituye la página completa por el error.

La interfaz no necesita distinguir visualmente entre causas técnicas que producen el mismo resultado para el usuario.

No se presentan directamente mensajes equivalentes a:

```text
500 Internal Server Error
NetworkError
Microsoft Graph no disponible
Excepción interna
```

---

## 24.9. Relación entre estados y colores semánticos

Los estados definidos reutilizan los colores semánticos establecidos en `7.3. Estados semánticos`.

Conceptualmente:

```text
Envío satisfactorio
=> Éxito

Límite de envíos
=> Advertencia

Error de carga
=> Error

Validación incorrecta
=> Error

Fallo de envío
=> Error
```

Los estados vacíos no utilizan el color de éxito solamente porque la operación técnica haya terminado correctamente.

Utilizan tratamiento neutral de contenido.

Los skeletons tampoco utilizan colores semánticos.

---

## 24.10. Relación entre estados y estructura

Un estado no debe eliminar regiones ajenas a la operación que lo produjo.

Conceptualmente:

```text
Error en una tarjeta
=> no elimina otras tarjetas

Error en contenido
=> no elimina navegación disponible

Error en cabecera
=> no elimina navegación disponible

Error en elementos subordinados de navegación
=> no elimina sección principal

Fallo de envío
=> no elimina formulario

Estado vacío de medios de contacto
=> no elimina formulario
```

La aplicación debe informar el estado allí donde afecta a la representación.

No debe convertir un fallo localizado en una pantalla global de error cuando las demás regiones continúan utilizables.

Las reglas responsive continúan aplicándose a los estados.

Un skeleton, error, estado vacío o contenido no encontrado utiliza la geometría correspondiente al ancho disponible y no fuerza la composición de escritorio.

---

# 25. Adaptación a diferentes pantallas

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

y debe modificar:

```text
Composición
Posición
Ancho disponible
Organización interna
Distribución de tarjetas
```

---

## 25.1. Puntos de ruptura

La aplicación utiliza tres composiciones principales:

```text
ancho >= 1360px
=> escritorio amplio

1024px <= ancho < 1360px
=> escritorio intermedio

ancho < 1024px
=> composición estrecha
```

No se introduce una sucesión adicional de puntos de ruptura únicamente para modificar cantidades fijas de columnas.

Los componentes que deben responder naturalmente al espacio disponible deben hacerlo sin depender de un número predeterminado de columnas.

---

## 25.2. Tipografía

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

---

## 25.3. Espaciado

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
padding de paneles       => 16px
gap entre tarjetas       => 16px
título / párrafo         => 12px
párrafo / párrafo        => 16px
secciones mayores        => 32px
grupos grandes           => 48px
altura de controles      => 48px
```

La composición estrecha no reduce automáticamente todos los espacios verticales.

No se utiliza `8px` como padding horizontal general de la aplicación.

---

## 25.4. Escritorio amplio

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

## 25.5. Umbral de Inicio

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

## 25.6. Escritorio intermedio

Cuando:

```text
1024px <= ancho < 1360px
```

la navegación continúa lateral y mantiene:

```text
224px
```

Las páginas internas continúan utilizando:

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

Durante toda la composición de escritorio permanecen:

```text
navegación lateral => 224px
cabecera expandida => 320px
cabecera compacta  => 112px
```

No se reducen progresivamente estas dimensiones para intentar mantener la composición de escritorio amplio.

---

## 25.7. Composición estrecha

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

---

## 25.8. Cabecera estrecha

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

Las alturas rígidas de:

```text
320px
112px
```

pertenecen al escritorio.

En la composición estrecha, la altura deriva del contenido, del padding y del ancho disponible.

---

## 25.9. Barra de navegación estrecha

La barra aparece inmediatamente debajo de la cabecera.

Presenta:

```text
Menú | Idioma | Tema
```

Idioma y Tema no se ocultan dentro de Menú.

La barra continúa disponible durante el desplazamiento junto con la cabecera compacta.

---

## 25.10. Apertura del menú

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

---

## 25.11. Grupos expandibles del menú

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

---

## 25.12. Selección de un destino desde el menú

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

---

## 25.13. Inicio en composición estrecha

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

## 25.14. Páginas internas en composición estrecha

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

---

## 25.15. Rejillas

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

---

## 25.16. Contenido ancho

La prioridad es:

```text
1. Reorganizar
2. Redimensionar proporcionalmente
3. Adaptar internamente
4. Desplazamiento horizontal propio
```

El desplazamiento horizontal de toda la página no se utiliza como solución para un componente interno.

Si resulta imprescindible:

```text
componente concreto
=> overflow horizontal
```

---

## 25.17. elementos visuales

Las imágenes, diagramas y demás elementos visuales utilizan el espacio disponible sin deformarse.

La regla general es:

```text
ancho necesario menor
=> redimensionar proporcionalmente
```

mientras el elemento continúe siendo legible.

Un elemento necesario no desaparece automáticamente por utilizar una pantalla estrecha.

---

## 25.18. Botones

La altura estándar permanece:

```text
48px
```

En escritorio, las acciones principales utilizan normalmente su ancho natural.

En composición estrecha, cuando forman parte del flujo principal:

```text
ancho => 100%
```

Los controles compactos de la navegación mantienen la geometría necesaria para constituir:

```text
Menú | Idioma | Tema
```

y no se transforman individualmente en botones de ancho completo.

---

## 25.19. Formulario

Los campos permanecen verticales y utilizan el ancho disponible.

El botón utiliza:

```text
ancho >= 1024px
=> ancho natural
=> altura 48px
=> padding horizontal 24px
```

```text
ancho < 1024px
=> ancho 100%
=> altura 48px
```

Durante:

```text
Enviando...
```

se conserva la misma regla de ancho.

---

## 25.20. Sobre mí

En escritorio debe mantenerse una composición horizontal entre texto y elemento visual.

En composición estrecha, cuando la disposición horizontal deja de caber correctamente:

```text
elemento visual
texto
```

o el orden editorial definido para el bloque se presentan verticalmente.

El orden del bloque no se invierte automáticamente por su índice.

Los elementos visuales mantienen sus proporciones.

---

## 25.21. Proyecto

En escritorio debe mantenerse:

```text
imagen | panel de metadatos
```

cuando el espacio resulta adecuado.

En composición estrecha:

```text
imagen
panel de metadatos
```

se presentan verticalmente.

El panel debe reorganizar también sus metadatos internamente.

La imagen se redimensiona proporcionalmente.

---

## 25.22. Certificado y Certificación

En escritorio debe utilizarse una composición horizontal cuando el contenido cabe correctamente.

En composición estrecha, una Certificación utiliza conceptualmente:

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

---

## 25.23. Artículo

En escritorio conserva el ancho de lectura definido.

En composición estrecha utiliza el ancho disponible y:

```text
padding horizontal => 16px
```

El orden editorial no cambia.

Las tablas, bloques de código, diagramas, grafos, imágenes y otros contenidos anchos utilizan la prioridad general definida en `25.16. Contenido ancho`.

---

## 25.24. Estados comunes

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

---

## 25.25. Principio de conservación

Responsive debe modificar:

```text
posición
disposición
ancho
cantidad natural de columnas
organización interna
```

pero no modifica arbitrariamente:

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

# 26. Accesibilidad

La accesibilidad forma parte de la estructura, la presentación y el comportamiento normal de la aplicación.

No constituye una representación paralela ni una segunda versión del sitio.

La misma interfaz debe proporcionar la información, jerarquía, relaciones, estados y mecanismos de interacción necesarios para su utilización mediante diferentes formas de acceso.

---

## 26.1. Nivel de conformidad

La referencia de accesibilidad del proyecto es:

```text
WCAG 2.2
Nivel AA
```

El cumplimiento adicional de requisitos correspondientes al nivel AAA debe conservarse cuando resulte adecuado.

Alcanzar un requisito AAA concreto no convierte AAA en el nivel general de conformidad del proyecto.

Una combinación o comportamiento que no alcance AAA debe permanecer cuando cumple el requisito AA correspondiente.

---

## 26.2. Orden estructural y navegación mediante teclado

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

La estructura correcta del documento tiene prioridad sobre el uso de `tabindex` cuando la estructura ya comporta lo mismo orden de lo visual. `tabindex` solamente se utiliza cuando un elemento necesita participar legítimamente en el orden normal de foco y su implementación lo requiere.


Un elemento gráfico que forma parte de un control no constituye un segundo objetivo de foco cuando no dispone de una acción propia.

---

## 26.3. Regiones semánticas y encabezados

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

La aplicación no incorpora un enlace adicional de salto al contenido principal.

La navegación entre regiones repetidas se apoya en la estructura semántica, los encabezados y la organización de la navegación.

---

## 26.4. Grupos expandibles

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

---

## 26.5. Nombres accesibles de controles

Todo control dispone de un nombre accesible que comunica su función.

Cuando existe texto visible suficiente:

```text
texto visible
=> nombre del control
```

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

## 26.6. Etiquetas y placeholders del formulario

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

---

## 26.7. Validación accesible de campos

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

## 26.8. Mensajes generales del formulario

Los mensajes generales permanecen visibles mientras continúan siendo pertinentes.

No desaparecen automáticamente después de un período breve.

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

## 26.9. Estado accesible de los skeletons

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

No se añade un texto oculto equivalente a:

```text
Cargando...
```

solamente para crear una representación adicional destinada a tecnologías de asistencia.

La animación visual del skeleton permanece mientras la operación continúa pendiente.

Cuando la carga termina con contenido, vacío o error, el skeleton desaparece y la unidad adopta el estado correspondiente.

---

## 26.10. Clasificación de imágenes

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

---

## 26.11. Imágenes decorativas

Las imágenes puramente decorativas no introducen información redundante.

Cuando corresponda, se implementan mediante recursos visuales de CSS.

Si una imagen decorativa necesita utilizar un elemento `<img>`, utiliza:

```html
alt=""
```

Una imagen que comunica información necesaria no utiliza `background-image` como sustitución de una imagen accesible.

---

## 26.12. Imágenes informativas

Una imagen informativa dispone de un texto alternativo que comunica la información esencial aportada por la imagen dentro de su contexto.

La alternativa no necesita describir cada detalle visual cuando esos detalles no forman parte de la información transmitida.

---

## 26.13. Imágenes funcionales

Cuando una imagen forma parte de una acción o constituye la representación principal de una acción, su alternativa comunica la función o el destino correspondiente.

La alternativa no se limita a describir la apariencia del recurso visual.

---

## 26.14. Imágenes de texto

Cuando resulta necesario utilizar una imagen que contiene texto y ese texto forma parte de la información que debe transmitirse, la alternativa incluye el contenido textual relevante.

---

## 26.15. Imágenes complejas

Una imagen compleja debe disponer de una alternativa breve y de una descripción adicional cuando la información completa no debe expresarse adecuadamente mediante `alt`.

La alternativa breve permite identificar el contenido sin convertir el atributo en una descripción excesivamente extensa.

---

## 26.16. Experiencias sensoriales específicas

Cuando la finalidad de una imagen incluye una experiencia visual o sensorial concreta y no constituye mera decoración, utiliza una identificación descriptiva compatible con esa función.

---

## 26.17. Iconos

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

---

## 26.18. Fotografía de la cabecera

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

---

## 26.19. Localización de información accesible

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

La localización debe modificar el sistema de escritura utilizado para representar el nombre.

---

## 26.20. Método de cálculo de contraste

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

## 26.21. Garantía cromática del tema claro

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

## 26.22. Tokens accesibles del tema claro

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

## 26.23. Auditoría de contraste del tema claro

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

Si la representación efectiva modifica el color, debe comprobarse el resultado efectivo.

---

## 26.24. Garantía cromática del tema oscuro

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

## 26.25. Tokens accesibles del tema oscuro

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

## 26.26. Auditoría de contraste del tema oscuro

Los colores del tema oscuro fueron comprobados según sus funciones y frente a todas las superficies en las que se permite su utilización.

Cuando un color debe aparecer en múltiples superficies, la tabla utiliza la combinación con menor contraste.

| Elemento                                    | Peor caso comprobado                                                   | Contraste        | AA      | AAA                      |
| ------------------------------------------- | ---------------------------------------------------------------------- | ---------------: | ------- | ------------------------ |
| Fondo principal `#0F141B`                   | Texto tenue `#8E97A3`                                                  | `6.2538873158:1` | Cumple  | No cumple                |
| Superficie primaria `#141B24`               | Texto tenue `#8E97A3`                                                  | `5.8627986079:1` | Cumple  | No cumple                |
| Superficie secundaria `#18212C`             | Texto tenue `#8E97A3`                                                  | `5.4965511091:1` | Cumple  | No cumple                |
| Texto principal `#F2F1EE`                   | sobre `#173328`                                                        | `12.0681208570:1`| Cumple  | Cumple                   |
| Texto secundario `#B8BDC6`                  | sobre `#173328`                                                        | `7.2261022755:1` | Cumple  | Cumple                   |
| Texto tenue `#8E97A3`                       | sobre `#173328`                                                        | `4.6122661865:1` | Cumple  | No cumple                |
| Borde funcional `#737B8B`                   | sobre `#173328`                                                        | `3.2032708892:1` | Cumple  | Cumple*                  |
| Rojo interactivo `#FE6162`                  | sobre `#173328`                                                        | `4.6088541127:1` | Cumple  | No cumple                |
| Rojo interactivo hover `#FE686A`            | sobre `#173328`                                                        | `4.8048821419:1` | Cumple  | No cumple                |
| Verde principal `#58B28D`                   | sobre `#173328`                                                        | `5.3016380075:1` | Cumple  | No cumple                |
| Verde hover `#4FA683`                       | sobre `#173328`                                                        | `4.6181145990:1` | Cumple  | No cumple                |
| Advertencia `#D6A34A`                       | sobre `#173328`                                                        | `5.9697345002:1` | Cumple  | No cumple                |
| Información `#6FA8FF`                       | sobre `#173328`                                                        | `5.6607425863:1` | Cumple  | No cumple                |
| Foco `#E2484D`                              | sobre `#173328`                                                        | `3.4193508748:1` | Cumple  | Cumple*                  |
| Placeholder `#8E97A3`                       | sobre `#173328`                                                        | `4.6122661865:1` | Cumple  | No cumple                |
| Botón principal normal                      | `#FFFFFF` sobre `#D6363B`                                              | `4.7190498141:1` | Cumple  | No cumple                |
| Botón principal hover                       | `#FFFFFF` sobre `#C92F35`                                              | `5.3278994839:1` | Cumple  | No cumple                |
| Botón secundario, texto                     | `#F2F1EE` sobre `#18212C`                                              | `14.3818765872:1`| Cumple  | Cumple                   |
| Botón secundario, borde                     | `#737B8B` contra `#18212C`                                             | `3.8174167420:1` | Cumple  | Cumple*                  |
| Enlace visitado `#BB7FD3`                   | sobre `#173328`                                                        | `4.6016656338:1` | Cumple  | No cumple                |
| Cabecera, nombre `#F2F1EE`                  | fotografía con capa negra mínima del `60%`; peor fondo `#666666`       | `5.0834876786:1` | Cumple  | Cumple*                  |
| Cabecera, descripción breve `#F2F1EE`       | fotografía con capa negra mínima del `60%`; peor fondo `#666666`       | `5.0834876786:1` | Cumple  | No cumple                |

`Cumple*` indica que el elemento no textual satisface el requisito de contraste no textual aplicable.

WCAG no incorpora un umbral AAA adicional independiente para contraste no textual.

El nombre de la cabecera satisface además el umbral AAA correspondiente a texto grande.

La descripción breve se evalúa como texto normal y no alcanza el umbral AAA de `7:1`.

La conformidad principal del proyecto permanece definida en AA.

---

## 26.27. Contraste sobre la fotografía de la cabecera

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

---

## 26.28. Bordes y separadores

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

El grosor continúa dependiendo de la función visual definida en `9. Bordes`.

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

El cambio de tema no modifica el significado de la línea.

---

## 26.29. Foco visible

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

Los demás estados continúan comunicando su propio significado.

---

## 26.30. Estados semánticos y color

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

## 26.31. Enlaces

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

---

## 26.32. Colores efectivos

La validación corresponde al color realmente representado.

Los valores comprobados no deben considerarse automáticamente válidos cuando se modifican mediante:

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
Token sin modificación
=> conserva el resultado comprobado

Color efectivo modificado
=> requiere comprobar el resultado efectivo
```

La comprobación debe utilizar el fondo efectivo sobre el que se representa el elemento.

La fotografía de la cabecera utiliza la excepción controlada definida en `26.27. Contraste sobre la fotografía de la cabecera`, donde el resultado efectivo se garantiza mediante la capa mínima establecida.

---

## 26.33. Título del documento

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

El separador forma parte de la convención definida para el sitio y no modifica la jerarquía de la información.

---

# Relación entre tema claro y tema oscuro

Los dos temas representan exactamente el mismo sitio.

Para un mismo ancho disponible deben compartir exactamente:

- estructura;
- contenido;
- selección editorial;
- cantidad de elementos;
- orden de los contenidos;
- tipografía;
- jerarquía;
- espaciado;
- bordes estructurales;
- dimensiones correspondientes a la composición activa;
- iconografía;
- navegación;
- composición de cabecera;
- estructura de las tarjetas;
- disposición de los metadatos;
- posición de los enlaces;
- contenido destacado;
- actualizaciones;
- campos de formularios;
- estructura de listados;
- estructura de páginas de detalle;
- reglas responsive;
- puntos de ruptura;
- reglas de los estados comunes;
- límites de las unidades de presentación;
- comportamiento de carga, vacío, error y contenido no encontrado;
- comportamiento de los estados del formulario.

Conceptualmente:

```text
Tema claro
|
+-- misma página
+-- mismo contenido
+-- mismo orden
+-- misma cantidad
+-- misma estructura responsive
+-- misma disposición para el mismo ancho
+-- mismos estados

Tema oscuro
|
+-- misma página
+-- mismo contenido
+-- mismo orden
+-- misma cantidad
+-- misma estructura responsive
+-- misma disposición para el mismo ancho
+-- mismos estados
```

Solamente deben variar los valores visuales necesarios para adaptar:

- fondos;
- superficies;
- colores de texto;
- colores de bordes;
- sombras;
- rojo;
- verde;
- estados interactivos;
- colores semánticos.

El cambio de tema no debe:

```text
Cambiar contenido
Cambiar elementos destacados
Cambiar actualizaciones
Cambiar el orden
Cambiar la cantidad de elementos
Cambiar la navegación
Cambiar el formato de las tarjetas
Cambiar la composición responsive
Cambiar los puntos de ruptura
Cambiar los espacios estructurales
Cambiar los textos
Cambiar los iconos
Cambiar los campos mostrados
Cambiar el significado de los estados
Cambiar las reglas de una unidad de presentación
Cambiar las reglas funcionales de accesibilidad
Cambiar la estructura semántica
Cambiar la navegación mediante teclado
```

El tema oscuro no debe ser considerado un diseño independiente.

El tema claro tampoco debe ser considerado una composición alternativa.

Ambos son representaciones visuales de la misma interfaz.

---

# Resumen de tokens principales

## Tipografía

```text
Título => Noto Serif Display / Cormorant Garamond / Georgia / serif
Cuerpo => Inter / Noto Sans / Arial / sans-serif
```

---

## Escalas tipográficas

```text
ancho >= 1024px
=> escala de escritorio

ancho < 1024px
=> escala de pantallas estrechas
```

### Escritorio

```text
Nombre => 64px
H1     => 48px
H2     => 36px
H3     => 28px
H4     => 22px
Lead   => 18px
Base   => 16px
Secundario => 14px
Auxiliar   => 12px
```

### Pantallas estrechas

```text
Nombre => 40px
H1     => 32px
H2     => 28px
H3     => 24px
H4     => 20px
Lead   => 18px
Base   => 16px
Secundario => 14px
Auxiliar   => 12px
```

---

## Tema claro

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

---

## Tema oscuro

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

### Cabecera del tema oscuro

```text
Texto                 => #F2F1EE
Capa negra mínima     => 60%
Peor fondo resultante => #666666
Contraste mínimo      => 5.0834876786:1
```

---

## Espaciado

```text
4
8
16
24
32
48
64
```

```text
Padding general >= 1024px => 24px
Padding general < 1024px  => 16px
```

---

## Puntos de ruptura

```text
>= 1360px
=> escritorio amplio

1024px–1359px
=> escritorio intermedio

< 1024px
=> composición estrecha
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

## Cabecera

```text
Escritorio expandida => 320px
Escritorio compacta  => 112px
Foto expandida       => 280px x 280px
Foto compacta        => 72px x 72px
Pantallas estrechas  => altura derivada del contenido
```

---

## Controles

```text
Altura estándar  => 48px
Icono navegación => 22px
Icono controles  => 20px
Border radius    => 0
```

---

## Iconografía

```text
Biblioteca => @tabler/icons-angular

Idioma             => IconWorld
Desplegar          => IconChevronDown
Contraer           => IconChevronUp
Tema claro         => IconSun
Tema oscuro        => IconMoon

Inicio             => IconHome
Sobre mí           => IconUser
Contactos          => IconMail
Certificaciones    => IconAward
Proyectos          => IconFolder
Artículos          => IconNotebook

Proyecto           => IconFolder
Artículo           => IconFileText
Certificado        => IconCertificate
Certificación      => IconAward
Acceso             => IconArrowRight
```

---

## Rejillas

```text
Columnas
=> tantas tarjetas completas como permita el ancho disponible

Siguiente tarjeta no cabe
=> nueva fila

Mínimo natural
=> una tarjeta por fila
```

No existe una cantidad fija de columnas.

---

## Contenido ancho

```text
1. Reorganizar
2. Redimensionar proporcionalmente
3. Adaptar internamente
4. Scroll horizontal del elemento
```

```text
Página completa
=> sin overflow horizontal provocado por un componente interno
```

---

## Accesibilidad

```text
Referencia            => WCAG 2.2
Nivel                  => AA
Orden visual           => orden del DOM => orden de foco
Foco tema claro        => 2px / offset 2px / #141414
Foco tema oscuro       => 2px / offset 2px / #E2484D
Skeleton visual        => fuera del contenido accesible
Unidad cargando        => aria-busy
Grupo expandible       => aria-expanded
Campo inválido         => aria-invalid
Error asociado         => aria-describedby
Resultado no urgente   => role="status"
Fallo de envío         => role="alert"
```

---

# Estado de la especificación

Los siguientes elementos de identidad visual quedan definidos:

1. tipografía concreta;
2. escala tipográfica de escritorio;
3. escala tipográfica de pantallas estrechas;
4. puntos de ruptura tipográficos;
5. alturas de línea;
6. pesos tipográficos;
7. paleta del tema claro;
8. paleta del tema oscuro;
9. estados visuales;
10. sombras;
11. bordes;
12. escala de espaciado;
13. adaptación del padding general;
14. proporciones del layout de escritorio amplio;
15. composición de escritorio intermedio;
16. composición de pantallas estrechas;
17. punto de ruptura natural de Inicio;
18. cabecera expandida y compacta de escritorio;
19. adaptación de cabecera en pantallas estrechas;
20. navegación lateral de escritorio;
21. navegación móvil;
22. apertura y cierre del menú móvil;
23. apertura y cierre de grupos expandibles;
24. restablecimiento de grupos después de la navegación;
25. permanencia de navegación y controles durante el desplazamiento;
26. foto y composición de cabecera;
27. biblioteca, mapeo, tamaños y uso de iconos;
28. mapeo de controles globales;
29. mapeo de navegación;
30. mapeo de tipos de contenido y acciones;
31. mapeo de iconos de Sobre mí;
32. mapeo de iconos de Contactos;
33. estructura visual de Inicio;
34. representación de contenido destacado;
35. área de exposición y actualizaciones;
36. reorganización de Actualizaciones en escritorio intermedio;
37. composición vertical de Inicio en pantallas estrechas;
38. estructura general de las páginas internas;
39. región variable de Contenido;
40. adaptación de componentes internos según espacio disponible;
41. reglas para contenido interno ancho;
42. composición visual de Sobre mí;
43. adaptación responsive de Sobre mí;
44. composición visual de Contactos;
45. formulario de contacto;
46. adaptación responsive del formulario;
47. lenguaje visual común de tarjetas;
48. rejillas adaptables de listados;
49. representación de certificados;
50. representación de certificaciones;
51. adaptación responsive de Certificado y Certificación;
52. listado y detalle de Proyectos;
53. representación del lenguaje principal de los proyectos;
54. adaptación responsive del detalle de Proyecto;
55. listado y detalle de Artículos;
56. representación de fechas de Artículos;
57. representación de contenido Markdown;
58. adaptación responsive de Artículos;
59. equivalencia estructural y de contenido entre los temas claro y oscuro;
60. equivalencia responsive entre los temas claro y oscuro;
61. unidad de presentación y límites de contenido independiente;
62. representación mediante skeleton durante la carga;
63. adaptación responsive de skeletons;
64. comportamiento de estados vacíos;
65. comportamiento de errores de carga;
66. tratamiento de elementos visuales obligatorios fallidos;
67. estados de carga y error de elementos subordinados de navegación;
68. estados de carga y error de cabecera;
69. representación de páginas y elementos no encontrados;
70. estado de envío en curso del formulario;
71. confirmación de envío satisfactorio;
72. representación de errores de validación;
73. comportamiento visible del honeypot;
74. representación del límite de envíos;
75. representación de fallos de envío;
76. relación entre estados y colores semánticos;
77. conservación de regiones independientes durante estados parciales;
78. conservación de contenido y jerarquía durante la adaptación responsive;
79. reorganización antes que eliminación de contenido;
80. prevención de desplazamiento horizontal de la página;
81. redimensionamiento proporcional de elementos visuales;
82. scroll horizontal limitado al componente cuando resulte necesario;
83. nivel WCAG 2.2 AA como referencia de accesibilidad;
84. coherencia entre orden visual, orden del DOM y orden de foco;
85. navegación mediante teclado y uso restringido de `tabindex`;
86. estructura semántica de cabecera, navegación y contenido principal;
87. jerarquía semántica de encabezados;
88. ausencia de movimiento automático de foco durante la carga inicial;
89. navegación estructural sin enlace adicional de salto al contenido principal;
90. semántica de los grupos expandibles;
91. comunicación mediante `aria-expanded` y relación mediante `aria-controls`;
92. exclusión del recorrido de foco de contenido oculto;
93. nombres accesibles de controles;
94. tratamiento accesible de iconos con texto e iconos sin texto;
95. asociación entre etiquetas y campos del formulario;
96. placeholders concretos del formulario;
97. representación semántica de errores de validación;
98. relación de errores mediante `aria-describedby`;
99. representación no interruptiva de confirmaciones y límites;
100. representación inmediata de fallos de envío;
101. semántica de unidades de carga mediante `aria-busy`;
102. exclusión accesible de las formas visuales del skeleton;
103. clasificación funcional de imágenes;
104. tratamiento de imágenes decorativas, informativas, funcionales, complejas y de texto;
105. alternativa textual localizada de la fotografía personal;
106. localización de textos relacionados con accesibilidad;
107. método y umbrales de cálculo de contraste;
108. paleta accesible definitiva del tema claro;
109. garantía de contraste de los usos permitidos del tema claro;
110. auditoría AA y AAA de la paleta clara;
111. token único de borde accesible del tema claro;
112. indicador de foco del tema claro;
113. comunicación de estados sin dependencia exclusiva del color;
114. identificación estructural y visual de enlaces;
115. comprobación de colores efectivos después de composiciones visuales;
116. actualización localizada del título del documento;
117. composición del título mediante información específica y nombre localizado del sitio;
118. localización de la representación del nombre personal dentro del título;
119. paleta accesible definitiva del tema oscuro;
120. garantía de contraste de todos los usos permitidos del tema oscuro;
121. separación entre rojo de primer plano y rojo de fondo en el tema oscuro;
122. auditoría AA y AAA de la paleta oscura;
123. borde funcional accesible del tema oscuro;
124. separador decorativo independiente del borde funcional;
125. indicador de foco accesible del tema oscuro;
126. estados semánticos accesibles del tema oscuro;
127. enlaces normales, hover y visitados accesibles del tema oscuro;
128. contraste de botones principales en estado normal y hover del tema oscuro;
129. contraste de botones secundarios del tema oscuro;
130. contraste del placeholder del tema oscuro;
131. contraste de texto principal, secundario y tenue sobre las superficies permitidas del tema oscuro;
132. garantía de contraste sobre fondos semánticos del tema oscuro;
133. capa mínima de contraste de la cabecera del tema oscuro;
134. garantía de contraste de la cabecera frente al caso de máxima luminosidad de la fotografía;
135. conservación de la capa mínima detrás de toda la región textual de la cabecera;
136. independencia entre la garantía de contraste de la cabecera y la fotografía concreta utilizada.

Los modelos visuales deben utilizar los iconos concretos establecidos en el mapeo de esta especificación.

Las representaciones visuales finales de escritorio continúan constituyendo la referencia de identidad y composición para las páginas definidas, complementadas por las reglas responsive establecidas para escritorio intermedio y pantallas estrechas.

Los estados comunes definidos forman parte de la referencia de comportamiento visual para todas las páginas y regiones correspondientes.

La adaptación responsive definida en esta especificación forma parte de la referencia cerrada de diseño.

Las decisiones de accesibilidad incluidas en esta especificación forman parte de la referencia cerrada de la etapa de accesibilidad hasta el punto actualmente definido.

La auditoría de contraste queda cerrada para los temas claro y oscuro dentro de los usos permitidos definidos por esta especificación.

La definición de accesibilidad continúa para los aspectos todavía pendientes antes de considerar completa la etapa de responsive y accesibilidad de `sitio`.

Esta especificación constituye la referencia base de identidad visual, responsive, accesibilidad definida y comportamiento visual para las siguientes etapas de diseño e implementación de `sitio`.
