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
- la navegación puede utilizar una densidad ligeramente mayor que el cuerpo principal.

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
| Texto tenue           | `#7A7E85` |
| Borde                 | `#D9D3CA` |
| Separador             | `#E6E0D8` |

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
| Borde                 | `#2A3340` |
| Separador             | `#202936` |

---

## 6.2. Colores de identidad

| Uso                    | Color     |
| ---------------------- | --------- |
| Rojo principal         | `#D6363B` |
| Rojo hover             | `#E2484D` |
| Rojo suave / selección | `#3A1618` |
| Verde principal        | `#58B28D` |
| Verde hover            | `#449977` |
| Verde suave            | `#173328` |

---

## 6.3. Colores de apoyo

| Uso           | Color     |
| ------------- | --------- |
| Casi negro    | `#0A0E13` |
| Blanco cálido | `#F7F5F1` |

---

# 7. Estados visuales

## 7.1. Tema claro

### Enlaces

```text
normal  => #B51E23
hover   => #99181C
visited => #7C3A65
focus   => #B51E23
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
borde => #D9D3CA
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
normal  => #E2484D
hover   => #F05C60
visited => #B77BCF
focus   => #E2484D
```

### Botón principal

```text
fondo normal => #D6363B
fondo hover  => #E2484D
texto        => #FFFFFF
```

### Botón secundario

```text
fondo => transparent
borde => #2A3340
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
| Advertencia | `#9A6A16` |
| Error       | `#B51E23` |
| Información | `#365E96` |

### Tema oscuro

| Estado      | Color     |
| ----------- | --------- |
| Éxito       | `#58B28D` |
| Advertencia | `#D6A34A` |
| Error       | `#E2484D` |
| Información | `#6FA8FF` |

---

## 7.4. Foco

Todos los elementos interactivos deben disponer de foco visible.

```css
outline: 2px solid currentColor;
outline-offset: 2px;
```

El color concreto debe corresponder al color principal interactivo del tema.

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

Las sombras pueden utilizarse en:

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
Borde estándar => #D9D3CA
Separador      => #E6E0D8
Acento rojo    => #B51E23
Acento verde   => #2F6D59
```

---

## 9.4. Tema oscuro

```text
Borde estándar => #2A3340
Separador      => #202936
Acento rojo    => #D6363B
Acento verde   => #58B28D
```

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

Cada una puede representar contenido subordinado.

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

Las secciones con contenido subordinado pueden expandirse y contraerse.

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

`Sitio-api` puede proporcionar identificadores o tipos de contenido necesarios para determinar qué debe representarse, pero no determina el nombre del icono de Tabler.

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

En pantallas estrechas, las acciones principales que forman parte del flujo de contenido pueden ocupar:

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

Cada actualización puede representar actividad relacionada con:

```text
Proyecto
Artículo
Certificado
Certificación
```

El acontecimiento puede representar:

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

Puede contener:

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
=> puede mantenerse

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

La reorganización se utiliza cuando puede cambiarse la disposición sin perder información o significado.

El redimensionamiento se utiliza para elementos que continúan siendo legibles después de reducirse.

La adaptación interna puede modificar la representación del componente.

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

La composición puede distribuir texto y elemento visual a uno u otro lado.

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

En escritorio puede mantenerse la composición horizontal definida editorialmente entre texto y elemento visual.

Cuando:

```text
ancho < 1024px
```

los bloques que no pueden conservar correctamente esa composición se reorganizan verticalmente.

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

Certificado y Certificación pueden presentar diferencias internas porque representan elementos distintos.

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

En escritorio puede mantenerse una composición horizontal mientras el espacio disponible permita representar correctamente sus regiones.

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

En escritorio puede mantenerse la composición horizontal entre imagen y panel de metadatos cuando el espacio disponible resulta adecuado.

Cuando:

```text
ancho < 1024px
```

la imagen y el panel de metadatos se reorganizan verticalmente.

Cada región utiliza el ancho disponible.

La imagen mantiene sus proporciones.

El panel de metadatos puede reorganizar también sus elementos internamente en disposición vertical cuando sea necesario.

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

Puede contener:

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

cuando esa información no modifica la acción que puede realizar.

---

## 24.1. Unidad de presentación

Los estados se aplican a unidades de presentación.

Una unidad de presentación constituye la menor entidad que puede comprenderse y utilizarse de forma independiente.

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

Por lo tanto, una colección puede presentar simultáneamente unidades que ya se encuentran completas y posiciones que todavía se encuentran cargando o que terminaron con error.

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

Si una parte necesaria de una unidad única no puede obtenerse o representarse correctamente, no se presenta el resto como un contenido completo.

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

Las unidades completas pueden presentarse a medida que se encuentran disponibles.

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

El estado vacío solamente puede aparecer después de completar correctamente la carga.

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

Un elemento visual puramente opcional o decorativo puede seguir sus propias reglas cuando su ausencia no invalida el contenido.

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

Las secciones independientes pueden alcanzar estados diferentes.

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

Cuando la cabecera no puede constituirse completamente:

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

El formulario permanece en la página y puede volver a utilizarse.

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
El nombre no puede superar los 100 caracteres.
```

```text
El apellido no puede superar los 100 caracteres.
```

```text
El motivo no puede superar los 200 caracteres.
```

```text
El mensaje no puede superar los 10000 caracteres.
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

Corresponde al backend determinar en ese momento si la solicitud puede continuar o si el límite sigue vigente.

---

### 24.8.7. Fallo de envío

Cuando los datos son válidos pero la operación no puede completarse:

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

y puede modificar:

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

Los componentes que pueden responder naturalmente al espacio disponible deben hacerlo sin depender de un número predeterminado de columnas.

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

El ancho interior principal puede utilizar hasta:

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

En escritorio puede mantenerse una composición horizontal entre texto y elemento visual.

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

En escritorio puede mantenerse:

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

El panel puede reorganizar también sus metadatos internamente.

La imagen se redimensiona proporcionalmente.

---

## 25.22. Certificado y Certificación

En escritorio puede utilizarse una composición horizontal cuando el contenido cabe correctamente.

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

Responsive puede modificar:

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
Rojo principal        => #B51E23
Verde principal       => #2F6D59
Borde                 => #D9D3CA
Separador             => #E6E0D8
```

---

## Tema oscuro

```text
Fondo principal       => #0F141B
Superficie primaria   => #141B24
Superficie secundaria => #18212C
Texto principal       => #F2F1EE
Texto secundario      => #B8BDC6
Rojo principal        => #D6363B
Verde principal       => #58B28D
Borde                 => #2A3340
Separador             => #202936
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
82. scroll horizontal limitado al componente cuando resulte necesario.

Los modelos visuales deben utilizar los iconos concretos establecidos en el mapeo de esta especificación.

Las representaciones visuales finales de escritorio continúan constituyendo la referencia de identidad y composición para las páginas definidas, complementadas por las reglas responsive establecidas para escritorio intermedio y pantallas estrechas.

Los estados comunes definidos forman parte de la referencia de comportamiento visual para todas las páginas y regiones correspondientes.

La adaptación responsive definida en esta especificación forma parte de la referencia cerrada de diseño.

La definición de accesibilidad continúa en la etapa correspondiente antes de considerar completa la etapa de responsive y accesibilidad de `sitio`.

Esta especificación constituye la referencia base de identidad visual, responsive y comportamiento visual para las siguientes etapas de diseño e implementación de `sitio`.
