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

El cambio de tema solamente cambia la representación visual correspondiente a cada paleta.

La estructura del sitio se adapta al espacio disponible sin convertir las composiciones estrechas en una reducción proporcional de la representación de escritorio.

La adaptación responsive debe conservar el contenido, la jerarquía, la identidad visual, los estados y el orden editorial.

El redimensionamiento del texto, la ampliación, el reflujo y los cambios de orientación deben conservar igualmente el contenido y la funcionalidad de la aplicación.

La interacción debe conservar la misma funcionalidad mediante teclado, ratón, tacto y lápiz cuando esos mecanismos se encuentran disponibles.

Las funciones propias de la aplicación no deben depender exclusivamente del paso del puntero, de gestos complejos, de movimientos de arrastre ni de movimientos físicos del dispositivo.

La accesibilidad debe validarse mediante una combinación de pruebas automatizadas y comprobaciones manuales. La comprobación manual no impide el flujo automatizado de la promoción. 

La totalidad de las pruebas automatizadas ejecutadas debe aprobarse antes de promover un cambio hacia la rama principal.

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

Los tamaños tipográficos se implementan mediante unidades relativas al tamaño de fuente raíz.

La raíz respeta el tamaño configurado por el usuario mediante:

```css
html {
    font-size: 100%;
}
```

No se establece:

```css
html {
    font-size: 16px;
}
```

como tamaño absoluto de la raíz.

Conceptualmente:

```text
1rem
=> tamaño de fuente raíz configurado por el usuario

Configuración habitual equivalente a 16px
=> 1rem = 16px
```

Los valores en píxeles indicados en esta sección representan la equivalencia visual de referencia cuando el tamaño raíz equivale a `16px`.

No constituyen la unidad utilizada para implementar `font-size`.

---

## 2.1. Escritorio

Se utiliza cuando:

```text
ancho >= 1024px
```

| Elemento                     | Tamaño     | Equivalencia de referencia |
| ---------------------------- | ---------: | -------------------------: |
| Nombre principal en cabecera | `4rem`     |                     `64px` |
| H1                           | `3rem`     |                     `48px` |
| H2                           | `2.25rem`  |                     `36px` |
| H3                           | `1.75rem`  |                     `28px` |
| H4                           | `1.375rem` |                     `22px` |
| Texto destacado / lead       | `1.125rem` |                     `18px` |
| Texto base                   | `1rem`     |                     `16px` |
| Texto secundario             | `0.875rem` |                     `14px` |
| Texto auxiliar / etiquetas   | `0.75rem`  |                     `12px` |

---

## 2.2. Pantallas estrechas

Se utiliza cuando:

```text
ancho < 1024px
```

| Elemento                     | Tamaño     | Equivalencia de referencia |
| ---------------------------- | ---------: | -------------------------: |
| Nombre principal en cabecera | `2.5rem`   |                     `40px` |
| H1                           | `2rem`     |                     `32px` |
| H2                           | `1.75rem`  |                     `28px` |
| H3                           | `1.5rem`   |                     `24px` |
| H4                           | `1.25rem`  |                     `20px` |
| Texto destacado / lead       | `1.125rem` |                     `18px` |
| Texto base                   | `1rem`     |                     `16px` |
| Texto secundario             | `0.875rem` |                     `14px` |
| Texto auxiliar / etiquetas   | `0.75rem`  |                     `12px` |

La escala cambia en el punto de ruptura correspondiente.

No se utiliza `clamp()` para producir una transición continua entre ambas escalas.

---

## 2.3. Aplicación de la escala

El cuerpo utiliza:

```css
body {
    font-size: 1rem;
}
```

Los controles nativos heredan la tipografía correspondiente de la aplicación.

Conceptualmente:

```css
button,
input,
textarea,
select {
    font: inherit;
}
```

La aplicación distribuye los tamaños de la escala de la siguiente manera:

```text
Nombre principal
=> escala de Nombre principal

H1
=> escala de H1

H2
=> escala de H2

H3
=> escala de H3

H4
=> escala de H4

Introducciones y textos destacados
=> 1.125rem

Párrafos
=> 1rem

Navegación principal
=> 1rem

Subelementos de navegación
=> 1rem

Botones
=> 1rem

Campos de formulario
=> 1rem

Selectores textuales
=> 1rem

Acciones y enlaces de interfaz
=> 1rem

Metadatos
=> 0.875rem

Fechas presentadas como metadatos
=> 0.875rem

Texto secundario
=> 0.875rem

Texto auxiliar
=> 0.75rem

Etiquetas pequeñas
=> 0.75rem

Placeholder
=> mismo tamaño que el texto del campo
=> 1rem
```

Los tamaños de texto de la interfaz no utilizan unidades dependientes directamente de la ventana para sustituir esta escala.

La cambiación del tamaño raíz realizada por el usuario debe cambiar proporcionalmente toda la escala tipográfica.

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

Los valores de `line-height` permanecen sin unidad para responder proporcionalmente al tamaño efectivo de la fuente.

Regla general:

- los títulos deben permanecer relativamente compactos;
- los textos de lectura deben disponer de mayor espacio vertical;
- la navegación debe utilizar una densidad ligeramente mayor que el cuerpo principal.

Los valores normales definidos en esta sección no impiden que el usuario sustituya el espaciado del texto según las reglas de accesibilidad definidas posteriormente.

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

`#202936` solamente debe utilizarse cuando la línea es decorativa y su ausencia no cambia la comprensión ni la identificación de un componente.

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

Los valores de espaciado visual normal no impiden que el espaciado textual configurado por el usuario requiera un crecimiento adicional de los contenedores.

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

El contenido textual de la navegación debe envolverse y aumentar verticalmente los elementos correspondientes cuando su tamaño efectivo ya no cabe en una sola línea.

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

La composición estrecha debe continuar reorganizándose correctamente hasta un ancho disponible de:

```text
320px CSS
```

para el contenido de desplazamiento vertical.

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
altura mínima       => 320px
padding horizontal  => 32px
padding vertical    => 24px
```

Debe mostrar:

- Fondo visual y foto juntos;
- nombre;
- descripción breve.

`320px` constituye la dimensión normal mínima.

La cabecera debe aumentar su altura cuando el tamaño efectivo o el espaciado del texto requieren más espacio para mantener completamente visibles el nombre y la descripción breve.

---

## 12.2. Estado compacto en escritorio

Cuando:

```text
ancho >= 1024px
```

utiliza:

```text
altura mínima       => 112px
padding horizontal  => 24px
padding vertical    => 16px
```

Debe mantener:

- Fondo visual y foto juntos;
- nombre.

Debe ocultar:

- descripción breve.

`112px` constituye la dimensión normal mínima.

La cabecera debe aumentar su altura cuando el nombre requiere más espacio después del redimensionamiento o cambiación del espaciado textual.

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

La cabecera no utiliza alturas máximas rígidas.

Su altura deriva de:

```text
Contenido
Padding
Ancho disponible
Tamaño efectivo del texto
Espaciado efectivo del texto
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

La sustitución futura de la fotografía no cambia esta garantía mientras permanezcan el color del texto y la capa mínima establecida.

Cuando el bloque textual aumenta debido al redimensionamiento o al espaciado del texto, la región cubierta por la capa debe aumentar junto con él.

---

# 13. Navegación

## 13.1. Dimensiones de escritorio

Cuando:

```text
ancho >= 1024px
```

la navegación utiliza:

```text
ancho                           => 224px
padding superior                => 16px
padding lateral                 => 16px
gap controles / menú            => 20px
altura mínima de ítem principal => 48px
padding horizontal de ítem      => 16px
gap icono / texto               => 12px
sangría de subítems             => 32px
altura mínima de subítem        => 48px
gap entre subítems              => 8px
altura máxima visible           => 100vh
overflow vertical               => auto
```

El ancho de `224px` permanece fijo mientras la navegación lateral sigue activa.

Los valores de `48px` son alturas mínimas.

Cada elemento debe aumentar verticalmente cuando su texto necesita más de una línea debido al tamaño efectivo, al espaciado o a la longitud del contenido.

La navegación no recorta ni trunca el texto para conservar estas alturas mínimas.

El área interactiva corresponde a toda la fila del elemento y no solamente al texto o al icono que contiene.

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

El crecimiento vertical producido por texto redimensionado o por un mayor espaciado textual debe seguir utilizando este desplazamiento vertical interno cuando la navegación supera la altura visible.

El desplazamiento corresponde al comportamiento normal de la región y no introduce una función personalizada basada en arrastre.

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

La barra debe reorganizar sus controles cuando el ancho disponible o el tamaño efectivo del texto no permite conservarlos correctamente en una sola fila.

No debe recortar texto ni producir desplazamiento horizontal de la página para conservar artificialmente la disposición horizontal.

Cada control independiente de la barra mantiene un objetivo interactivo mínimo de `48px x 48px CSS`.

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

La apertura y el cierre ocurren mediante una activación explícita.

Pasar el puntero sobre el grupo no cambia por sí mismo su estado abierto o cerrado.

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

Cuando la selección produce una nueva página mediante navegación interna, después de completar el cierre del menú y representar el destino se aplica la gestión de foco definida en `26.35. Cambio de página y foco`.

La barra:

```text
Menú | Idioma | Tema
```

sigue disponible durante el desplazamiento junto con la cabecera compacta.

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

El crecimiento vertical de la cabecera provocado por el texto no exige aumentar proporcionalmente esta fotografía.

---

## 14.2. Estado compacto de escritorio

Área visual aproximada correspondiente a la fotografía:

```text
72px x 72px
```

La fotografía permanece visible.

El crecimiento vertical necesario para acomodar el nombre no cambia automáticamente esta dimensión.

---

## 14.3. Pantallas estrechas

Por debajo de:

```text
1024px
```

la fotografía sigue integrada en `Fondo visual y foto juntos`.

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

Los medios de contacto utilizan el icono correspondiente a su tipo.

El mapeo definido es:

| Tipo de medio         | Icono concreto      |
| --------------------- | ------------------- |
| Red profesional       | `IconBrandLinkedin` |
| Repositorio de código | `IconBrandGithub`   |
| Sitio web             | `IconWorldWww`      |
| Correo electrónico    | `IconMail`          |
| Teléfono              | `IconPhone`         |
| Mensajería            | `IconBrandWhatsapp` |

Las tarjetas de Contactos no utilizan una imagen de contenido como alternativa al icono.

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

Los tamaños definidos no cambian el icono seleccionado por el mapeo.

El redimensionamiento del texto no obliga a redimensionar estos iconos cuando su función sigue correctamente representada junto al texto correspondiente.

El tamaño del icono no determina el tamaño del objetivo interactivo que lo contiene.

---

## 15.9. Selector de idioma

En escritorio, la presentación normal utiliza:

```text
altura mínima      => 48px
ancho normal       => 104px
padding horizontal => 12px
border-radius      => 0
borde              => 1px
font-size          => 1rem
```

Debe permanecer directamente visible.

No debe estar oculto dentro de una sección de configuración.

El ancho de `104px` constituye la referencia normal de presentación.

Cuando el texto necesita más espacio debido al idioma, al redimensionamiento o al espaciado configurado por el usuario, el selector debe aumentar su espacio o la composición que lo contiene debe reorganizarse.

No debe recortar ni truncar el texto para conservar `104px`.

En pantallas estrechas sigue directamente disponible dentro de:

```text
Menú | Idioma | Tema
```

No se traslada al interior de `Menú`.

El objetivo interactivo mantiene como mínimo:

```text
48px x 48px CSS
```

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

El control utiliza solamente un icono visible.

Su geometría de:

```text
48px x 48px
```

permanece fija mientras su contenido visible sigue siendo exclusivamente iconográfico.

El icono interior debe mantener el tamaño definido en `15.8. Tamaños`.

La superficie interactiva corresponde a todo el control de `48px x 48px`.

En pantallas estrechas sigue directamente disponible dentro de:

```text
Menú | Idioma | Tema
```

Debe permitir cambiar directamente entre:

```text
tema claro
tema oscuro
```

El cambio de tema no cambia la página representada.

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
altura mínima      => 48px
padding horizontal => 24px
font-size          => 1rem
font-weight        => 600
border-radius      => 0
```

Con una raíz equivalente a `16px`:

```text
font-size => 16px
```

En escritorio utiliza su ancho natural cuando no existe una regla específica diferente.

En pantallas estrechas, las acciones principales que forman parte del flujo de contenido deben ocupar:

```text
ancho => 100%
```

cuando corresponde a la composición definida.

La altura mínima permanece en:

```text
48px
```

El botón debe aumentar su altura cuando el texto redimensionado, el texto localizado o el espaciado configurado por el usuario necesitan más espacio.

No debe recortar, ocultar ni truncar el texto para conservar una altura exacta de `48px`.

El objetivo interactivo completo debe disponer como mínimo de:

```text
48px x 48px CSS
```

---

## 15.12. Botón secundario

Base:

```text
altura mínima      => 48px
padding horizontal => 24px
font-size          => 1rem
borde              => 1px
border-radius      => 0
```

Las reglas responsive de ancho siguen la composición de la acción correspondiente.

El botón debe aumentar su altura cuando el contenido textual necesita más espacio.

El objetivo interactivo completo debe disponer como mínimo de:

```text
48px x 48px CSS
```

---

## 15.13. Objetivos interactivos

Los objetivos interactivos independientes propios de la aplicación utilizan como tamaño mínimo:

```text
48px x 48px CSS
```

La medida corresponde al área que acepta la interacción y no al tamaño visual del texto, icono u otro contenido situado dentro del control.

Conceptualmente:

```text
Control
=> mínimo 48px x 48px CSS

Icono interior
=> debe ser menor
=> pertenece al mismo objetivo
```

Esta regla se aplica a:

```text
Ítems principales de navegación
Subelementos de navegación
Controles de grupos expandibles
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

Los objetivos independientes no utilizan la excepción de separación entre objetivos como estrategia normal para reducir su tamaño.

Los enlaces incluidos dentro de párrafos u otros bloques de texto permanecen integrados en el flujo textual.

No se transforman en controles de `48px` de altura cuando su función pertenece directamente al texto en el que aparecen.

La regla de `48px x 48px CSS` supera:

```text
24px x 24px CSS
=> mínimo de 2.5.8 Tamaño del objetivo (mínimo), nivel AA

44px x 44px CSS
=> mínimo de 2.5.5 Tamaño del objetivo (mejorado), nivel AAA
```

para los objetivos independientes a los que se aplica.

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

Las tarjetas de contenido destacado utilizan la misma regla de rejilla adaptable establecida en `20.3. Rejilla`.

El acceso al listado completo constituye un objetivo interactivo independiente y aplica el mínimo definido en `15.13. Objetivos interactivos`.

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

El cambio de tema no cambia la estructura interna, el orden, el contenido ni la disposición correspondiente al ancho disponible.

Las tarjetas deben aumentar su altura cuando el texto redimensionado o el espaciado configurado por el usuario requieren más espacio.

No debe limitarse su altura para mantener una alineación visual a costa del contenido.

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

Debe admitir variaciones en la cantidad disponible sin cambiar la estructura general del área.

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

La acción explícita constituye el objetivo interactivo y aplica el tamaño mínimo definido para controles independientes.

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

Las rejillas internas siguen presentando tantas tarjetas completas como permita el ancho disponible.

La composición debe continuar funcionando sin pérdida de contenido ni funcionalidad hasta un ancho de `320px CSS`.

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

La variación ocurre dentro de esta región sin cambiar:

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

El mismo principio se aplica cuando el espacio disponible se reduce por la ampliación del navegador.

---

## 17.4. Contenido interno ancho

La página completa no debe adquirir desplazamiento horizontal debido a un componente interno.

Cuando un componente supera el espacio disponible, la prioridad es:

```text
1. Reorganizar
2. Redimensionar proporcionalmente
3. Adaptar internamente
4. Utilizar desplazamiento horizontal solamente en el elemento cuando la estructura bidimensional sea necesaria
```

La reorganización se utiliza cuando debe cambiarse la disposición sin perder información o significado.

El redimensionamiento se utiliza para elementos que siguen siendo legibles después de reducirse.

La adaptación interna debe cambiar la representación del componente.

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

El desplazamiento horizontal se utiliza solamente cuando las alternativas anteriores perjudican el uso, la comprensión o el significado porque la estructura bidimensional necesita conservarse.

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

La pertenencia a una categoría concreta, como tabla, código o diagrama, no constituye por sí sola una excepción al reflujo.

El desplazamiento propio utiliza el mecanismo normal proporcionado por el navegador y no depende de una implementación personalizada que requiera arrastrar un elemento de interfaz.

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

## 18.5. Adaptación responsive

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
| icono                        |
| ---------------------------- |
| nombre del medio             |
| enlace del medio             |
--------------------------------
```

La tarjeta contiene:

```text
Icono
Tipo de medio
Enlace
```

El icono debe utilizar el mapeo definido en `15.7. Contactos`.

Las tarjetas de Contactos no utilizan imágenes de contenido como representación del medio.

El propio enlace del medio es un vínculo que lleva hacia el medio directamente.

Cada enlace constituye un objetivo interactivo independiente y dispone como mínimo de un área interactiva de:

```text
48px x 48px CSS
```

La tarjeta completa no se convierte en un segundo objetivo interactivo si la acción ya corresponde al enlace explícito.

---

## 19.2. Rejilla de contactos

Las tarjetas se organizan horizontalmente mientras exista espacio disponible.

La cantidad de columnas depende del ancho disponible.

Cuando una nueva tarjeta ya no cabe correctamente en la fila actual, sigue en la siguiente.

Los medios presentes dependen de los datos disponibles.

No se define un número fijo de tarjetas por fila.

El crecimiento del texto debe reducir naturalmente la cantidad de tarjetas que caben en una fila antes de recortar el contenido de una tarjeta.

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

Los campos de una línea utilizan como mínimo:

```text
altura => 48px
```

El campo de varias líneas utiliza una altura superior a ese mínimo de acuerdo con su función.

Todos los campos conservan un área interactiva mínima compatible con:

```text
48px x 48px CSS
```

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

Los mecanismos técnicos de validación, envío y protección no cambian la identidad visual general de la página.

---

## 19.5. Adaptación responsive

Los campos permanecen verticales y utilizan todo el ancho disponible de la región del formulario.

No se reorganizan horizontalmente en escritorio.

El botón principal utiliza:

```text
ancho >= 1024px
=> ancho natural
=> altura mínima 48px
=> padding horizontal 24px
```

Cuando:

```text
ancho < 1024px
```

utiliza:

```text
ancho         => 100%
altura mínima => 48px
```

La misma regla se aplica durante `enviando...`.

La adaptación no cambia los estados ni el contenido del formulario.

Los campos, etiquetas, placeholders, mensajes de validación y controles deben crecer o reorganizarse cuando el redimensionamiento o el espaciado del texto requieren más espacio.

La capacidad de interacción mediante tacto, ratón o lápiz no cambia entre las composiciones responsive.

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
=> icono
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
=> sigue en la fila siguiente
```

La cantidad de columnas constituye una consecuencia del espacio disponible y del tamaño efectivo del contenido.

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

El aumento del texto debe reducir la cantidad de columnas cuando sea necesario antes de producir recorte, superposición o desplazamiento horizontal de la página.

---

## 20.4. Altura y alineación

Las tarjetas pertenecientes a una misma rejilla deben mantener una composición visual coherente.

La estructura interna debe permitir que diferencias razonables de longitud de texto no destruyan la alineación general.

Cuando existe una acción explícita al final de la tarjeta, su posición debe permanecer visualmente consistente dentro de la rejilla.

La coherencia visual no establece una altura máxima que impida el crecimiento de una tarjeta cuando su contenido textual necesita más espacio.

---

## 20.5. Interacción

La tarjeta completa nunca debe convertirse implícitamente en enlace, siempre habrá un enlace específico para la acción explícita.

En Contactos, el propio valor del medio constituye el enlace y no se añade una segunda acción redundante.

Cada acción independiente dentro de una tarjeta utiliza como mínimo:

```text
48px x 48px CSS
```

de área interactiva.

La superficie interactiva corresponde al enlace o control explícito y no se extiende artificialmente a toda la tarjeta.

El paso del puntero cambia el tratamiento visual del control o de la tarjeta como retroalimentación, pero no revela una función que no esté disponible sin ese estado.

---

# 21. Certificaciones

La sección visible sigue denominándose:

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

Cuando el espacio disponible deja de permitir esta composición, incluido el crecimiento provocado por el redimensionamiento del texto, el detalle se reorganiza verticalmente.

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

Las acciones de verificación y regreso que constituyen objetivos independientes aplican el tamaño mínimo general de interacción.

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

Las acciones explícitas constituyen objetivos independientes y aplican el tamaño mínimo general definido para interacción.

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

No debe cambiarse automáticamente solamente porque un repositorio haya recibido una actualización técnica reciente.

---

## 22.5. Adaptación responsive del detalle

En escritorio debe mantenerse la composición horizontal entre imagen y panel de metadatos cuando el espacio disponible resulta adecuado.

Cuando el espacio disponible deja de resultar adecuado, incluido el crecimiento del texto:

```text
imagen
panel de metadatos
```

se presentan verticalmente.

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

Los cambios de idioma definidos editorialmente dentro del contenido forman parte de la estructura semántica del artículo.

El procesamiento de Markdown debe conservar la información necesaria para que esos cambios continúen identificados en la representación resultante.

El frontend no analiza automáticamente el texto para inferir el idioma de un fragmento.

Los enlaces integrados dentro del contenido textual siguen siendo enlaces de texto y utilizan las excepciones normativas correspondientes a objetivos incluidos dentro de un bloque textual.

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

Los textos del artículo utilizan la misma escala tipográfica relativa de la aplicación.

---

## 23.5. Adaptación responsive del artículo

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

cuando esa información no cambia la acción que debe realizar.

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

No se utiliza `Cargando...` como sustitución general del contenido.

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

La representación sigue utilizando:

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

Siguen disponibles:

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

Si falla la obtención de los elementos subordinados, la sección principal sigue disponible.

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
altura mínima       => 320px
Fondo visual y foto juntos
Nombre
Descripción breve
```

La geometría efectiva debe acompañar el crecimiento que correspondería al contenido textual con el tamaño y espaciado activos.

### Cabecera compacta pendiente en escritorio

Cuando corresponde la geometría compacta, respeta aproximadamente:

```text
altura mínima       => 112px
Fondo visual y foto juntos
Nombre
```

La geometría efectiva debe acompañar el crecimiento que correspondería al nombre con el tamaño y espaciado activos.

### Pantallas estrechas

Cuando:

```text
ancho < 1024px
```

el skeleton no utiliza una altura máxima rígida.

Respeta aproximadamente la geometría responsive resultante del contenido, el padding, el ancho disponible, el tamaño del texto y su espaciado.

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

Si una parte obligatoria todavía se encuentra pendiente, la unidad sigue en estado de carga.

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

Las acciones de navegación de estos estados aplican el tamaño mínimo general de los objetivos interactivos independientes.

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
=> temporalmente no cambiables
=> siguen disponibles para el recorrido de foco

Botón
=> enviando...
=> no permite iniciar un segundo envío simultáneo
=> sigue disponible para el recorrido de foco
```

No se utiliza:

```text
skeleton
overlay de página completa
spinner global
```

para representar esta operación.

La navegación permanece disponible.

El inicio del envío no desplaza el foco.

Cuando la operación se inicia desde el botón de envío, el foco permanece en ese control.

Cuando el envío se inicia mediante teclado desde otro campo, el foco permanece en ese campo.

Mientras la operación sigue pendiente, cualquier nueva tentativa de envío por el host debe ser ignorada por el backend antes de generar una segunda solicitud, independientemente de si procede de una activación del botón o de otra forma de envío del formulario.

Cuando la operación termina, los campos vuelven a quedar disponibles para edición y el control vuelve a:

```text
enviar
```

independientemente del resultado recibido.

El frontend no conserva una condición local que impida futuros intentos basándose en una respuesta anterior del backend.

El ancho del botón durante el envío conserva las reglas responsive definidas para el estado normal.

El tamaño y el espaciado del texto durante este estado deben seguir las mismas reglas de crecimiento del control que en el estado normal.

La interacción mediante puntero conserva la misma semántica de activación que el estado normal.

La indisponibilidad temporal durante el envío no introduce una activación diferente basada en presión, gesto o dispositivo.

La semántica accesible concreta de este estado se define en `26.8. Mensajes generales del formulario`.

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

El usuario debe identificar qué campo requiere cambio.

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

No debe convertir un fallo localizado en una pantalla global de error cuando las demás regiones siguen utilizables.

Las reglas responsive siguen aplicándose a los estados.

Un skeleton, error, estado vacío o contenido no encontrado utiliza la geometría correspondiente al ancho disponible y no fuerza la composición de escritorio.

El redimensionamiento y el espaciado del texto se aplican igualmente a los estados comunes y sus mensajes.

Las acciones presentes dentro de un estado mantienen las mismas reglas de objetivo interactivo y de activación mediante puntero que sus equivalentes en contenido normal.

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

No se introduce una sucesión adicional de puntos de ruptura únicamente para cambiar cantidades fijas de columnas.

Los componentes que deben responder naturalmente al espacio disponible deben hacerlo sin depender de un número predeterminado de columnas.

No se crea un punto de ruptura adicional en `320px`.

La composición estrecha debe continuar funcionando hasta ese ancho.

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

Los tamaños se implementan mediante `rem` según `2. Escala tipográfica`.

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

Esta composición debe continuar funcionando hasta:

```text
320px CSS
```

sin pérdida de contenido ni funcionalidad y sin desplazamiento horizontal de la página para el contenido normal.

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

## 25.9. Barra de navegación estrecha

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

La apertura y el cierre requieren una activación explícita y no se producen solamente por pasar el puntero sobre el control.

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

El objetivo interactivo corresponde a toda la fila del grupo.

El icono no constituye un objetivo separado.

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

Cuando la navegación produce una nueva página, el cierre del menú y del grupo precede al foco programático sobre el encabezado principal de la página de destino.

El comportamiento de foco se encuentra definido en `26.35. Cambio de página y foco`.

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

El crecimiento del texto forma parte de la comprobación de si la composición sigue cabiendo correctamente.

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

El tamaño efectivo del texto participa en el espacio necesario de cada tarjeta.

---

## 25.16. Contenido ancho

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

## 25.17. elementos visuales

Las imágenes, diagramas y demás elementos visuales utilizan el espacio disponible sin deformarse.

La regla general es:

```text
ancho necesario menor
=> redimensionar proporcionalmente
```

mientras el elemento continúe siendo legible.

Un elemento necesario no desaparece automáticamente por utilizar una pantalla estrecha, por ampliación ni por cambio de orientación.

---

## 25.18. Botones

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

## 25.19. Formulario

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

## 25.20. Sobre mí

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

## 25.21. Proyecto

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

## 25.22. Certificado y Certificación

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

## 25.23. Artículo

En escritorio conserva el ancho de lectura definido mientras ese ancho sigue siendo compatible con el espacio disponible.

En composición estrecha utiliza el ancho disponible y:

```text
padding horizontal => 16px
```

El orden editorial no cambia.

Las tablas, bloques de código, diagramas, grafos, imágenes y otros contenidos anchos utilizan la prioridad general definida en `25.16. Contenido ancho`.

El texto debe refluir dentro del ancho disponible.

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

Los mensajes y controles de estado siguen las mismas reglas de redimensionamiento y reflujo que el contenido normal.

---

## 25.25. Principio de conservación

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

## 25.26. Redimensionamiento y reflujo

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

## 25.27. Orientación

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

Los criterios de nivel A siguen siendo obligatorios para la conformidad AA cuando no existe un criterio AA equivalente que sustituya la misma exigencia.

El nivel propio de un criterio de WCAG no se cambia para adaptarlo al nivel general del proyecto.

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

La estructura correcta del documento tiene prioridad sobre el uso de `tabindex` cuando la estructura ya comporta lo mismo orden de lo visual.

`tabindex` solamente se utiliza cuando existe una necesidad concreta de foco que no queda resuelta mediante el comportamiento nativo.

El valor:

```html
tabindex="-1"
```

solamente debe utilizarse para permitir que un elemento reciba foco programáticamente sin incorporarlo al recorrido secuencial mediante `Tab`.

Este comportamiento se utiliza en el encabezado principal de una nueva página según `26.35. Cambio de página y foco`.

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

Esta regla corresponde a la carga inicial del sitio.

El cambio de una página por otra mediante navegación interna utiliza el comportamiento específico definido en `26.35. Cambio de página y foco`.

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

El control completo mantiene el mínimo de:

```text
48px x 48px CSS
```

y su apertura o cierre requiere una activación explícita.

---

## 26.5. Nombres accesibles de controles

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

El placeholder utiliza el mismo tamaño tipográfico del texto del campo:

```text
1rem
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

No se añade un texto oculto equivalente a `Cargando...` solamente para crear una representación adicional destinada a tecnologías de asistencia.

La animación visual del skeleton permanece mientras la operación sigue pendiente.

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

El tratamiento accesible de los iconos se encuentra definido en `26.17. Iconos`.

---

## 26.11. Imágenes decorativas

Las imágenes puramente decorativas no introducen información redundante.

Cuando corresponda, se implementan mediante recursos visuales de CSS.

Si una imagen decorativa necesita utilizar un elemento `<img>`, utiliza `alt=""`.

Na imagen que comunica información necesaria, no utiliza `background-image` como sustitución de una imagen accesible.

---

## 26.12. Imágenes informativas

Una imagen informativa dispone de un texto alternativo que comunica la información esencial aportada por la imagen dentro de su contexto.

La alternativa no necesita describir cada detalle visual cuando esos detalles no forman parte de la información transmitida.

---

## 26.13. Imágenes funcionales

Cuando una imagen forma parte de una acción o constituye la representación principal de una acción, su alternativa comunica la función o el destino correspondiente.

La alternativa no se limita a describir la apariencia del elemento visual.

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

Los iconos utilizados en las tarjetas de Contactos siguen estas mismas reglas.

Cuando el tipo de medio ya se encuentra identificado mediante texto visible suficiente, el icono funciona como apoyo visual y no se anuncia de forma independiente.

Cuando el icono pertenece a un control, su tamaño visual no limita la superficie interactiva del control.

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

La fotografía de la cabecera pertenece a la estructura del sitio y utiliza la regla específica definida en esta sección.

No depende de los contratos de imágenes de contenido descritos en `26.10. Clasificación de imágenes`.

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

La localización debe cambiar el sistema de escritura utilizado para representar el nombre.

Las alternativas textuales que forman parte de contenido localizado son proporcionadas por `sitio-api` junto con la variante correspondiente del contenido.

Cuando una alternativa textual pertenece a una variante presentada en un idioma diferente del idioma principal del documento, debe quedar incluida dentro del contexto semántico del idioma correspondiente a esa variante.

---

## 26.20. Idioma semántico

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

## 26.21. Método de cálculo de contraste

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

## 26.22. Garantía cromática del tema claro

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

## 26.23. Tokens accesibles del tema claro

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

## 26.24. Auditoría de contraste del tema claro

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

## 26.25. Garantía cromática del tema oscuro

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

## 26.26. Tokens accesibles del tema oscuro

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

## 26.27. Auditoría de contraste del tema oscuro

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

## 26.28. Contraste sobre la fotografía de la cabecera

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

## 26.29. Bordes y separadores

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

El grosor sigue dependiendo de la función visual definida en `9. Bordes`.

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

## 26.30. Foco visible

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

## 26.31. Estados semánticos y color

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

## 26.32. Enlaces

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

Un enlace que constituye una acción independiente utiliza el objetivo mínimo definido en `15.13. Objetivos interactivos`.

Un enlace situado dentro de un bloque de texto conserva su presentación textual y utiliza la excepción normativa aplicable a objetivos integrados en texto.

---

## 26.33. Colores efectivos

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

La fotografía de la cabecera utiliza la excepción controlada definida en `26.28. Contraste sobre la fotografía de la cabecera`, donde el resultado efectivo se garantiza mediante la capa mínima establecida.

---

## 26.34. Título del documento

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

## 26.35. Cambio de página y foco

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

Cuando ese encabezado pertenece a una variante presentada mediante un idioma de respaldo, debe conservar además el idioma semántico definido en `26.20. Idioma semántico`.

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

## 26.36. Redimensionamiento, reflujo, espaciado y orientación

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

Las escalas completas son las definidas en `2. Escala tipográfica`.

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

Estos valores no sustituyen los valores visuales normales definidos en `3. Alturas de línea` ni en `10. Espaciado`.

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

## 26.37. Interacción por puntero y tacto

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

Los componentes cuyo contenido necesita desplazamiento horizontal según `25.16. Contenido ancho` utilizan el comportamiento normal de desplazamiento del navegador.

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

Los controles formados solamente por iconos siguen utilizando el nombre accesible localizado definido en `26.5. Nombres accesibles de controles`.

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

El cambio entre orientación vertical y horizontal definido en `25.27. Orientación` no constituye actuación mediante movimiento.

Conceptualmente:

```text
Cambio de orientación
=> cambia el espacio disponible
=> aplica reglas responsive mediante el tamaño de la pantalla
=> no ejecuta una función adicional
```

No existe una función que dependa de sensores de movimiento para su operación normal.

---

## 26.38. Pruebas de accesibilidad

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

Las pruebas automatizadas propias deben reproducir el cálculo definido en `26.21. Método de cálculo de contraste`.

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

Las combinaciones del tema claro deben conservar como mínimo los resultados registrados en `26.24. Auditoría de contraste del tema claro`.

Las combinaciones del tema oscuro deben conservar como mínimo los resultados registrados en `26.27. Auditoría de contraste del tema oscuro`.

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

La prueba debe incluir todos los niveles de la escala tipográfica definidos en `2. Escala tipográfica`.

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
- comportamiento de los estados del formulario;
- estructura semántica de idioma;
- escala tipográfica relativa;
- reglas de redimensionamiento del texto;
- reglas de reflujo;
- reglas de espaciado del texto;
- comportamiento entre orientaciones;
- tamaños mínimos de objetivos interactivos;
- mecanismos de entrada disponibles;
- comportamiento de activación mediante puntero;
- reglas de interacción mediante tacto;
- ausencia de dependencia funcional de `hover`;
- reglas de cancelación del puntero;
- ausencia de arrastre obligatorio;
- comportamiento de etiquetas visibles y nombres accesibles;
- reglas de pruebas funcionales de accesibilidad;
- porcentaje obligatorio de aprobación de las pruebas automatizadas;
- criterios de comprobación manual aplicables.

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
+-- mismas reglas de redimensionamiento y reflujo
+-- mismos objetivos interactivos
+-- mismos mecanismos de entrada
+-- misma interacción funcional
+-- misma estrategia de validación de accesibilidad

Tema oscuro
|
+-- misma página
+-- mismo contenido
+-- mismo orden
+-- misma cantidad
+-- misma estructura responsive
+-- misma disposición para el mismo ancho
+-- mismos estados
+-- mismas reglas de redimensionamiento y reflujo
+-- mismos objetivos interactivos
+-- mismos mecanismos de entrada
+-- misma interacción funcional
+-- misma estrategia de validación de accesibilidad
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
Cambiar el idioma semántico del documento
Cambiar el idioma semántico de las partes
Cambiar la escala tipográfica
Cambiar las reglas de redimensionamiento
Cambiar las reglas de reflujo
Cambiar las reglas de espaciado del texto
Cambiar el comportamiento entre orientaciones
Cambiar el tamaño mínimo de los objetivos interactivos
Cambiar los mecanismos de entrada admitidos
Cambiar la activación mediante puntero
Introducir dependencia funcional de hover
Cambiar las reglas de cancelación del puntero
Introducir arrastre obligatorio
Cambiar la relación entre etiqueta visible y nombre accesible
Cambiar el criterio de aceptación automatizada
Eliminar comprobaciones manuales aplicables
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

Raíz
=> font-size: 100%

Texto base
=> 1rem
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
Nombre     => 4rem     => 64px de referencia
H1         => 3rem     => 48px de referencia
H2         => 2.25rem  => 36px de referencia
H3         => 1.75rem  => 28px de referencia
H4         => 1.375rem => 22px de referencia
Lead       => 1.125rem => 18px de referencia
Base       => 1rem     => 16px de referencia
Secundario => 0.875rem => 14px de referencia
Auxiliar   => 0.75rem  => 12px de referencia
```

### Pantallas estrechas

```text
Nombre     => 2.5rem   => 40px de referencia
H1         => 2rem     => 32px de referencia
H2         => 1.75rem  => 28px de referencia
H3         => 1.5rem   => 24px de referencia
H4         => 1.25rem  => 20px de referencia
Lead       => 1.125rem => 18px de referencia
Base       => 1rem     => 16px de referencia
Secundario => 0.875rem => 14px de referencia
Auxiliar   => 0.75rem  => 12px de referencia
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

## Cabecera

```text
Escritorio expandida => min-height 320px
Escritorio compacta  => min-height 112px
Foto expandida       => 280px x 280px
Foto compacta        => 72px x 72px
Pantallas estrechas  => altura derivada del contenido
```

---

## Controles

```text
Altura mínima textual       => 48px
Objetivo interactivo propio => mínimo 48px x 48px CSS
Subítem de navegación       => min-height 48px
Campo de una línea          => min-height 48px
Icono navegación            => 22px
Icono controles             => 20px
Border radius               => 0

Selector de tema
=> 48px x 48px
=> control iconográfico

Icono dentro de control
=> debe ser menor que 48px
=> superficie interactiva permanece en el control completo

Enlace integrado en texto
=> conserva flujo textual
=> excepción normativa correspondiente
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
=> tantas tarjetas completas como permita el ancho disponible y el tamaño efectivo del contenido

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
4. Scroll horizontal del elemento solamente para estructura bidimensional necesaria
```

```text
Página completa
=> sin overflow horizontal provocado por un componente interno
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

## Accesibilidad

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

# Estado de la especificación

Los siguientes elementos de identidad visual quedan definidos:

1. tipografía concreta;
2. escala tipográfica relativa de escritorio;
3. escala tipográfica relativa de pantallas estrechas;
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
136. independencia entre la garantía de contraste de la cabecera y la fotografía concreta utilizada;
137. distinción entre carga inicial y cambio interno de página para la gestión de foco;
138. ausencia de movimiento programático de foco durante la carga inicial;
139. foco programático en el encabezado principal después de una navegación interna hacia una nueva página;
140. uso de `tabindex="-1"` en el encabezado principal para permitir foco programático sin cambiar el recorrido normal mediante teclado;
141. conservación de `main` como región semántica sin convertirla en destino automático de foco;
142. conservación del foco durante actualizaciones que permanecen dentro de la misma página;
143. tratamiento de las páginas de contenido no encontrado como destinos completos de navegación;
144. cierre del menú de navegación estrecho antes de trasladar el foco al encabezado principal de la nueva página;
145. comunicación del cambio de contexto mediante el título del documento y el encabezado principal sin una región `aria-live` adicional;
146. estado ocupado del formulario durante el envío mediante `aria-busy`;
147. estado temporal de solo lectura de los campos mediante `readonly`;
148. conservación de los campos en el recorrido de foco durante el envío;
149. indisponibilidad semántica temporal del botón mediante `aria-disabled`;
150. conservación del botón de envío en el recorrido de foco;
151. bloqueo funcional de cualquier segundo envío mientras existe una solicitud pendiente;
152. anuncio no interruptivo de `enviando...` mediante `role="status"`;
153. ubicación de la región de progreso fuera del formulario marcado como ocupado;
154. conservación del foco en el control desde el que se inició el envío;
155. restauración de los estados semánticos del formulario antes de comunicar el resultado final;
156. ausencia de un anuncio adicional de finalización cuando el resultado ya comunica el desenlace;
157. presencia obligatoria de `src` y `alt` en todas las imágenes de contenido;
158. utilización de una cadena textual o una cadena vacía como valor de `alt`, sin utilizar `null`;
159. responsabilidad de `sitio-api` sobre la determinación del valor final de `alt` según la función y el contexto de la imagen;
160. representación directa de `alt` por `sitio` sin generación, sustitución, vaciado ni reclasificación por parte del frontend;
161. posibilidad de utilizar un mismo elemento visual con alternativas distintas cuando cambia su función entre representaciones;
162. tratamiento informativo o funcional de las imágenes de `Sobre mí` según su función editorial;
163. alternativa vacía para las imágenes de proyectos utilizadas en representaciones resumidas;
164. alternativa informativa para la imagen principal de un proyecto en su detalle;
165. alternativa vacía para las imágenes principales de artículos utilizadas en representaciones resumidas;
166. determinación editorial de la alternativa de la imagen principal de un artículo en su detalle;
167. clasificación individual de las imágenes incluidas dentro del contenido Markdown;
168. alternativa vacía para las imágenes de certificados y certificaciones utilizadas en representaciones resumidas;
169. alternativa informativa para las imágenes de certificados y certificaciones en sus páginas de detalle;
170. disposición de información extensa de documentos mediante contenido textual accesible en lugar de concentrarla únicamente en `alt`;
171. utilización exclusiva de iconos como representación visual de los medios de Contactos;
172. exclusión de imágenes de contenido de las tarjetas de Contactos;
173. utilización de `3.1.1 Idioma de la página`, nivel A, para la declaración del idioma principal al no existir un criterio AA equivalente para esa exigencia;
174. utilización de `3.1.2 Idioma de las partes`, nivel AA, para las partes cuyo idioma difiere del idioma principal;
175. ausencia de un criterio AAA adicional específico para la declaración semántica mediante `lang`;
176. utilización de etiquetas BCP 47 válidas en las declaraciones lingüísticas;
177. declaración del idioma activo del sistema como idioma principal del documento;
178. actualización del idioma principal del documento después de una selección manual de idioma;
179. conservación del idioma principal durante la navegación interna que mantiene el mismo idioma activo;
180. conservación del idioma del documento cuando una unidad utiliza un idioma de respaldo;
181. declaración del idioma real de las variantes presentadas mediante respaldo;
182. aplicación de la declaración lingüística solamente a la región correspondiente al contenido que utiliza ese idioma;
183. conservación del idioma activo del sistema en los textos propios de la interfaz y en el aviso de utilización de un idioma de respaldo;
184. declaración independiente del idioma de cada unidad dentro de colecciones que presentan variantes en idiomas diferentes;
185. separación semántica entre contenido localizado y acciones de interfaz cuando utilizan idiomas diferentes dentro del mismo componente;
186. utilización del idioma real de la variante en sus encabezados y alternativas textuales;
187. conservación del idioma semántico del encabezado principal cuando recibe foco programático;
188. declaración de cambios lingüísticos internos en el elemento semántico correspondiente;
189. aplicación de las excepciones establecidas por WCAG para nombres propios, términos técnicos, idiomas indeterminados y expresiones incorporadas al idioma circundante;
190. conservación de los cambios lingüísticos editoriales durante el procesamiento del contenido Markdown;
191. ausencia de detección automática del idioma por análisis del texto;
192. utilización de herencia cuando el contenido mantiene el mismo idioma de su ancestro;
193. ausencia de `lang=""` cuando el idioma es conocido;
194. actualización de la declaración lingüística cuando cambia la variante representada;
195. utilización del idioma de la solicitud que produjo el contenido presentado sin añadir una propiedad general adicional al contrato para determinar el idioma de la variante;
196. implementación de la escala tipográfica mediante unidades relativas `rem`;
197. respeto al tamaño de fuente raíz configurado por el usuario mediante `font-size: 100%`;
198. equivalencia de referencia de la escala tipográfica basada en una raíz habitual de `16px` sin fijar ese valor como tamaño absoluto;
199. aplicación de la escala tipográfica a encabezados, párrafos, navegación, controles, campos, acciones, metadatos, etiquetas y textos auxiliares;
200. herencia tipográfica de los controles nativos de formulario;
201. utilización de dimensiones mínimas en los componentes textuales cuya presentación normal dispone de una altura definida;
202. crecimiento obligatorio de los contenedores cuando el texto redimensionado necesita más espacio;
203. ausencia de recorte, truncamiento, ocultación y superposición como solución al crecimiento del texto;
204. cumplimiento de `1.4.4 Redimensionamiento del texto`, nivel AA, mediante soporte hasta `200%`;
205. ausencia de restricciones sobre la ampliación normal del navegador;
206. utilización de una configuración de ventana gráfica compatible con zoom;
207. ausencia de `user-scalable=no`, `maximum-scale=1` o restricciones equivalentes;
208. reutilización de las mismas reglas responsive cuando el zoom reduce el ancho CSS disponible;
209. cumplimiento de `1.4.10 Reflujo`, nivel AA, para contenido de desplazamiento vertical hasta `320px CSS`;
210. ausencia de desplazamiento horizontal de la página para contenido normal durante el reflujo;
211. reducción natural de las rejillas hasta una tarjeta por fila cuando corresponde;
212. reorganización de los componentes horizontales cuando dejan de caber correctamente;
213. limitación del desplazamiento horizontal propio a contenido cuya estructura bidimensional necesita conservarse;
214. aplicación de la excepción de desplazamiento horizontal según la necesidad real del contenido y no según su categoría;
215. adaptación de cadenas extensas dentro de sus contenedores cuando su división conserva el significado;
216. cumplimiento de `1.4.12 Espaciado del texto`, nivel AA;
217. soporte de interlineado equivalente a `1.5` veces el tamaño de fuente sin pérdida;
218. soporte de espacio posterior a párrafos equivalente a `2` veces el tamaño de fuente sin pérdida;
219. soporte de espaciado entre letras equivalente a `0.12` veces el tamaño de fuente sin pérdida;
220. soporte de espaciado entre palabras equivalente a `0.16` veces el tamaño de fuente sin pérdida;
221. conservación del contenido y la funcionalidad cuando los valores de espaciado se aplican simultáneamente;
222. cumplimiento de `1.3.4 Orientación`, nivel AA, sin exigir una orientación concreta;
223. funcionamiento completo del sitio en orientación vertical;
224. funcionamiento completo del sitio en orientación horizontal;
225. aplicación de las reglas responsive según las dimensiones resultantes después de un cambio de orientación;
226. ausencia de bloqueo de orientación, exigencia de rotación o funciones exclusivas de una orientación;
227. ausencia de una excepción funcional que requiera orientación específica;
228. relación con `1.4.8 Presentación visual`, nivel AAA, sin declarar su cumplimiento completo únicamente por las decisiones de redimensionamiento y reflujo;
229. cumplimiento de `1.4.13 Contenido señalado con el puntero o en foco`, nivel AA, sin depender actualmente de contenido adicional activado por estos estados;
230. obligación de que cualquier contenido adicional futuro activado mediante puntero o foco sea descartable, apuntable y persistente;
231. cumplimiento de `2.5.1 Gestos del puntero`, nivel A, al no exigir gestos multipunto ni recorridos específicos para utilizar funciones propias del sitio;
232. conservación formal del nivel A de `2.5.1` al no existir un criterio AA equivalente que sustituya esa exigencia;
233. cumplimiento de `2.5.2 Cancelación del puntero`, nivel A, mediante acciones completadas por la activación normal y no por la presión inicial;
234. conservación formal del nivel A de `2.5.2` al no existir un criterio AA equivalente que sustituya esa exigencia;
235. cumplimiento de `2.5.3 Etiqueta en el nombre`, nivel A, mediante inclusión del texto visible dentro del nombre accesible;
236. conservación formal del nivel A de `2.5.3` al no existir un criterio AA equivalente que sustituya esa exigencia;
237. cumplimiento de `2.5.4 Actuación mediante movimiento`, nivel A, mediante ausencia de funciones activadas por movimientos físicos del dispositivo o del usuario;
238. conservación formal del nivel A de `2.5.4` al no existir un criterio AA equivalente que sustituya esa exigencia;
239. cumplimiento de `2.5.7 Movimientos de arrastre`, nivel AA, mediante ausencia de funciones que requieran arrastre como único mecanismo;
240. obligación de proporcionar una operación equivalente sin arrastre si una interacción de arrastre se incorpora posteriormente;
241. cumplimiento de `2.5.8 Tamaño del objetivo (mínimo)`, nivel AA;
242. adopción de `48px x 48px CSS` como mínimo general para los objetivos interactivos independientes propios de `sitio`;
243. superación del mínimo normativo de `24px x 24px CSS` establecido por `2.5.8`;
244. cambio de los subelementos de navegación desde `36px` hasta `48px` de altura mínima;
245. utilización del control completo como superficie interactiva en lugar de limitar el objetivo al texto, icono o elemento SVG interior;
246. aplicación del mínimo de `48px x 48px CSS` a navegación, grupos expandibles, controles globales, botones, campos, acciones de tarjetas, accesos de listado, acciones de regreso y enlaces independientes de Contactos;
247. conservación de los enlaces integrados dentro de texto como objetivos textuales mediante la excepción normativa correspondiente;
248. cumplimiento adicional de `2.5.5 Tamaño del objetivo (mejorado)`, nivel AAA, mediante objetivos independientes de `48px x 48px CSS`, respetando las excepciones normativas;
249. utilización del estado `hover` exclusivamente como retroalimentación visual adicional;
250. ausencia de funciones, contenido necesario o cambios de estado disponibles exclusivamente mediante `hover`;
251. apertura y cierre de grupos expandibles solamente mediante activación explícita;
252. utilización de una activación sencilla equivalente mediante ratón, tacto y lápiz;
253. ausencia de funciones propias que requieran gestos multipunto, recorridos específicos, formas dibujadas o pulsaciones prolongadas;
254. conservación de los gestos normales del navegador para desplazamiento, ampliación y demás funciones propias del agente de usuario;
255. ausencia de acciones definitivas ejecutadas mediante `pointerdown`, `mousedown` o `touchstart` como mecanismo general;
256. posibilidad de cancelar una interacción de puntero antes de completar la activación normal del control;
257. ausencia de arrastre obligatorio para reordenar, navegar, cambiar estados, seleccionar opciones o completar operaciones;
258. cumplimiento adicional de `2.5.6 Mecanismos de entrada concurrentes`, nivel AAA;
259. conservación simultánea de ratón, tacto, lápiz y teclado cuando los mecanismos se encuentran disponibles;
260. ausencia de desactivación de un mecanismo de entrada debido a la detección o utilización de otro;
261. ausencia de funciones activadas mediante sacudidas, inclinación u otros movimientos físicos;
262. tratamiento del cambio de orientación exclusivamente como cambio del espacio disponible y no como orden funcional;
263. conservación de las mismas reglas de interacción por puntero y tacto en los temas claro y oscuro;
264. integración de `@axe-core/playwright` con las pruebas ejecutadas mediante Playwright;
265. utilización de `axe-core` como motor de auditoría automática de accesibilidad;
266. configuración de la auditoría mediante las etiquetas `wcag2a`, `wcag2aa`, `wcag21a`, `wcag21aa` y `wcag22aa`;
267. exigencia de `0` violaciones en cada análisis automático de `axe-core`;
268. envío de los resultados no determinables automáticamente a comprobación manual;
269. conservación de la comprobación manual aunque la auditoría automática no informe violaciones;
270. exigencia de `100%` de aprobación de todas las pruebas automatizadas ejecutadas;
271. bloqueo de la promoción hacia `main` cuando una sola prueba automatizada falla;
272. utilización del porcentaje real de pruebas aprobadas en lugar de una puntuación estimativa de accesibilidad;
273. cobertura de accesibilidad para cada tipo conceptual de página;
274. cobertura independiente de los estados que cambian estructura, semántica o comportamiento;
275. comprobación de las representaciones visuales dependientes del tema en claro y oscuro;
276. cobertura de contenido en el idioma del sistema, contenido mediante respaldo, colecciones multilingües y cambios lingüísticos internos;
277. utilización de datos de prueba con cadenas extensas, contenido ancho y demás condiciones necesarias para ejercitar los límites de la interfaz;
278. comprobación automática y manual de la navegación mediante teclado;
279. comprobación automática de la gestión del foco mediante `document.activeElement`;
280. comprobación manual de la perceptibilidad, claridad y ausencia de ocultación del indicador de foco;
281. comprobación automática de la estructura semántica, relaciones y estados ARIA;
282. comprobación automática y manual de los nombres accesibles;
283. comprobación automática de `lang` y revisión manual de su correspondencia con el idioma real del contenido;
284. comprobación automática de la presencia y conservación de `alt` y revisión manual de la adecuación de las alternativas;
285. reproducción automática de la fórmula de contraste definida por la especificación;
286. fallo automático cuando una combinación cromática permitida queda por debajo del umbral correspondiente;
287. conservación de la comprobación manual para fondos variables y para la cobertura real de la capa de contraste de la cabecera;
288. comprobación automática del redimensionamiento del texto hasta `200%`;
289. comprobación automática del reflujo a `320px CSS`;
290. comprobación manual del caso equivalente de `1280px CSS` con ampliación del navegador al `400%`;
291. aplicación simultánea de los valores `1.5`, `2`, `0.12` y `0.16` durante las pruebas de espaciado textual;
292. comprobación de funcionamiento en orientación vertical y horizontal;
293. medición automática mediante `getBoundingClientRect()` de objetivos interactivos independientes de al menos `48px x 48px CSS`;
294. exclusión de los enlaces integrados dentro del texto de la exigencia general de `48px x 48px CSS`;
295. comprobación de los mismos flujos mediante ratón, tacto emulado y teclado cuando la automatización permite reproducirlos;
296. comprobación de la disponibilidad funcional en ausencia de `hover`;
297. comprobación de que las acciones definitivas no se ejecutan únicamente mediante `pointerdown`, `mousedown` o `touchstart`;
298. comprobación de la posibilidad de cancelar una interacción de puntero antes de completar la activación;
299. comprobación de ausencia de arrastre obligatorio;
300. comprobación automatizada de todos los estados semánticos del formulario;
301. comprobación automatizada de `aria-busy`, `aria-hidden` y exclusión del foco durante los estados de carga;
302. comprobación conjunta de `<title>`, `H1`, foco y cierre de navegación durante los cambios internos de página;
303. obligación de comprobar manualmente el comportamiento real mediante lector de pantalla;
304. exclusión de la comparación píxel a píxel como criterio suficiente de conformidad de accesibilidad;
305. integración de las pruebas automatizadas de accesibilidad dentro de la validación anterior a la promoción hacia `main`;
306. obligación de completar las comprobaciones manuales aplicables antes de promover cambios que afecten estructura, semántica, interacción, navegación, estados, presentación accesible o contenido editorial relacionado con accesibilidad.

Los modelos visuales deben utilizar los iconos concretos establecidos en el mapeo de esta especificación.

Las representaciones visuales finales de escritorio siguen constituyendo la referencia de identidad y composición para las páginas definidas, complementadas por las reglas responsive establecidas para escritorio intermedio y pantallas estrechas.

Los estados comunes definidos forman parte de la referencia de comportamiento visual para todas las páginas y regiones correspondientes.

La adaptación responsive definida en esta especificación forma parte de la referencia cerrada de diseño.

Las decisiones de accesibilidad incluidas en esta especificación forman parte de la referencia cerrada de la etapa de accesibilidad.

La auditoría de contraste queda cerrada para los temas claro y oscuro dentro de los usos permitidos definidos por esta especificación.

La gestión de contexto y foco durante los cambios de página queda cerrada para la navegación interna de la aplicación.

La semántica accesible del estado de envío en curso del formulario queda cerrada mediante el estado ocupado del formulario, los campos temporalmente de solo lectura, la indisponibilidad semántica y funcional del control de envío, la comunicación no interruptiva del progreso y la conservación del foco.

Las alternativas textuales de las imágenes de contenido quedan cerradas mediante la clasificación funcional correspondiente a cada representación, la responsabilidad de `sitio-api` sobre el valor final de `alt`, la representación directa de ese valor por `sitio`, las reglas concretas para `Sobre mí`, proyectos, artículos, certificados y certificaciones, y la utilización exclusiva de iconos en las tarjetas de Contactos.

El idioma semántico queda cerrado mediante la declaración del idioma activo del sistema en el documento, la declaración del idioma real de las partes que difieren de él, la conservación del idioma de las variantes presentadas mediante respaldo, la separación entre contenido e interfaz dentro de unidades multilingües y la conservación de los cambios lingüísticos definidos editorialmente dentro del contenido.

El redimensionamiento, el reflujo, el espaciado del texto y la orientación quedan cerrados mediante la escala tipográfica relativa, el soporte del aumento del texto hasta `200%`, la conservación del zoom del navegador, el reflujo hasta `320px CSS`, el crecimiento obligatorio de los contenedores textuales, la limitación del desplazamiento horizontal a contenido bidimensional necesario, el soporte de los valores de espaciado definidos por WCAG y el funcionamiento completo en ambas orientaciones.

La interacción por puntero y tacto queda cerrada mediante objetivos interactivos independientes de al menos `48px x 48px CSS`, la ampliación de los subelementos de navegación a `48px` de altura mínima, la independencia funcional respecto de `hover`, la activación sencilla mediante ratón, tacto y lápiz, la cancelación antes de completar una activación, la ausencia de arrastre y gestos complejos obligatorios, la conservación de los mecanismos de entrada concurrentes, la correspondencia entre etiqueta visible y nombre accesible y la ausencia de actuación funcional mediante movimiento físico.

Las pruebas de accesibilidad quedan cerradas mediante la integración de `@axe-core/playwright`, la exigencia de `0` violaciones automatizadas dentro del alcance configurado, la aprobación obligatoria del `100%` de la suite automatizada, la cobertura por páginas, estados, temas, contextos lingüísticos y mecanismos de interacción, y la conservación de comprobaciones manuales para los aspectos que requieren evaluación humana o tecnologías de asistencia reales.

Ninguna prueba manual impide el flujo automatizado de la promoción. Las pruebas manuales sinven de comprobación humana, por lo que no es posible formar parte del flujo automatizado de la promoción.

La etapa de responsive y accesibilidad queda cerrada mediante las reglas de adaptación estructural, contraste, foco, semántica, idioma, alternativas textuales, redimensionamiento, reflujo, orientación, interacción por puntero y tacto y la estrategia de pruebas definida en esta especificación.

Esta especificación constituye la referencia base de identidad visual, responsive, accesibilidad definida y comportamiento visual para las siguientes etapas de diseño e implementación de `sitio`.
