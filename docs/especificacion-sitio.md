# Especificación técnica de identidad visual

## Estado

Esta especificación define la identidad visual base del frontend de `sitio`.

La especificación fue derivada de las decisiones de diseño tomadas durante la definición visual del proyecto y de las representaciones finales aprobadas para los temas claro y oscuro.

Su objetivo es servir como referencia técnica durante el diseño de las páginas y la futura implementación con Angular y Tailwind CSS.

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

La cabecera combina en una única composición:

- fondo visual;
- retrato;
- nombre;
- descripción breve.

La navegación utiliza iconografía como apoyo visual.

El tema claro y el tema oscuro mantienen la misma identidad, estructura y jerarquía visual.

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

## 2.1. Escritorio

| Elemento                     |  Tamaño |
| ---------------------------- | -------: |
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

## 2.2. Pantallas pequeñas

| Elemento         |  Tamaño |
| ---------------- | -------: |
| Nombre principal | `40px` |
| H1               | `32px` |
| H2               | `28px` |
| H3               | `24px` |
| Texto base       | `16px` |
| Texto secundario | `14px` |
| Texto auxiliar   | `12px` |

---

# 3. Alturas de línea

| Elemento         | `line-height` |
| ---------------- | --------------: |
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

| Elemento                       |    Peso |
| ------------------------------ | ------: |
| Nombre principal               | `700` |
| H1                             | `700` |
| H2                             | `700` |
| H3                             | `600` |
| Lead                           | `500` |
| Texto base                     | `400` |
| Texto secundario               | `400` |
| Etiquetas pequeñas            | `600` |
| Navegación principal          | `500` |
| Elemento activo de navegación | `600` |
| Botones                        | `600` |

---

# 5. Paleta del tema claro

## 5.1. Colores neutrales

| Uso                   | Color       |
| --------------------- | ----------- |
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

| Uso                     | Color       |
| ----------------------- | ----------- |
| Rojo principal          | `#B51E23` |
| Rojo hover              | `#99181C` |
| Rojo suave / selección | `#F7E9E8` |
| Verde principal         | `#2F6D59` |
| Verde hover             | `#255847` |
| Verde suave             | `#E8F2EE` |

---

## 5.3. Colores de apoyo

| Uso            | Color       |
| -------------- | ----------- |
| Negro de apoyo | `#0E0E0E` |
| Blanco puro    | `#FFFFFF` |

---

# 6. Paleta del tema oscuro

## 6.1. Colores neutrales

| Uso                   | Color       |
| --------------------- | ----------- |
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

| Uso                     | Color       |
| ----------------------- | ----------- |
| Rojo principal          | `#D6363B` |
| Rojo hover              | `#E2484D` |
| Rojo suave / selección | `#3A1618` |
| Verde principal         | `#58B28D` |
| Verde hover             | `#449977` |
| Verde suave             | `#173328` |

---

## 6.3. Colores de apoyo

| Uso            | Color       |
| -------------- | ----------- |
| Casi negro     | `#0A0E13` |
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
fondo  => #FFFFFF
borde  => #D9D3CA
texto  => #141414
```

### Navegación activa

```text
fondo            => #F7E9E8
barra izquierda  => #B51E23
texto             => #B51E23
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
fondo  => transparent
borde  => #2A3340
texto  => #F2F1EE
```

### Navegación activa

```text
fondo            => #3A1618
barra izquierda  => #D6363B
texto             => #F2F1EE
```

---

## 7.3. Estados semánticos

### Tema claro

| Estado       | Color       |
| ------------ | ----------- |
| Éxito       | `#2F6D59` |
| Advertencia  | `#9A6A16` |
| Error        | `#B51E23` |
| Información | `#365E96` |

### Tema oscuro

| Estado       | Color       |
| ------------ | ----------- |
| Éxito       | `#58B28D` |
| Advertencia  | `#D6A34A` |
| Error        | `#E2484D` |
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
- tarjetas destacadas;
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

Si posteriormente algún elemento concreto requiere un radio por razones funcionales o visuales, deberá definirse expresamente.

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

| Uso                                      |  Espacio |
| ---------------------------------------- | -------: |
| Padding general de la aplicación        | `24px` |
| Separación navegación / contenido      | `24px` |
| Padding interno de navegación           | `16px` |
| Separación entre bloques de navegación | `24px` |
| Separación entre elementos de menú     | `12px` |
| Separación idioma / tema                | `16px` |
| Padding de paneles                       | `16px` |
| Gap entre columnas principales           | `24px` |
| Gap entre tarjetas pequeñas             | `16px` |
| Título / párrafo                       | `12px` |
| Párrafo / párrafo                      | `16px` |
| Secciones mayores                        | `32px` |
| Grupos grandes                           | `48px` |

---

# 11. Proporciones del layout

## 11.1. Escritorio

### Navegación

```text
224px
```

Ancho fijo.

### Columna principal

```text
mínimo => 720px
óptimo => 1fr
```

### Área de exposición de la landing

```text
320px
```

Ancho fijo.

### Ancho máximo del contenido interior principal

```text
960px
```

### Ancho máximo total previsto

```text
1504px
```

---

## 11.2. Landing

La landing utiliza tres regiones horizontales:

```text
| navegación | contenido principal | área de exposición |
|   224px     |        1fr          |       320px        |
```

---

## 11.3. Páginas internas

Las páginas internas no utilizan el área de exposición.

```text
| navegación | contenido principal |
|   224px     |        1fr          |
```

---

## 11.4. Pie

El sitio no dispone de pie global.

El contenido termina cuando termina la página.

---

# 12. Cabecera

La cabecera es una única composición visual.

Incluye:

- fondo visual;
- retrato;
- nombre;
- descripción breve.

No debe dividirse visualmente en una imagen de fondo y una fotografía completamente independientes.

---

## 12.1. Estado expandido

```text
altura             => 320px
padding horizontal => 32px
padding vertical   => 24px
```

Debe mostrar:

- fondo visual completo;
- retrato;
- nombre;
- descripción breve.

---

## 12.2. Estado compacto

```text
altura             => 112px
padding horizontal => 24px
padding vertical   => 16px
```

Debe mantener:

- fondo visual reducido;
- retrato;
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

# 13. Navegación

## 13.1. Dimensiones

```text
ancho                         => 224px
padding superior              => 16px
padding lateral               => 16px
gap controles / menú          => 20px
altura de ítem principal      => 48px
padding horizontal de ítem    => 16px
gap icono / texto             => 12px
sangría de subítems           => 32px
altura de subítem             => 36px
gap entre subítems            => 8px
altura máxima visible         => 100vh
overflow vertical             => auto
```

---

## 13.2. Estructura

La navegación comienza con los controles globales:

```text
Idioma | Tema
```

Después aparecen las secciones:

```text
Inicio
Perfil
Certificaciones
Proyectos
Contactos
Blog
```

---

## 13.3. Jerarquía expandible

Las secciones con contenido subordinado pueden expandirse.

Ejemplo:

```text
Proyectos
    Proyecto 1
    Proyecto 2
    Proyecto 3
    Ver todos
```

`Ver todos` siempre aparece al final.

No debe aparecer antes de los elementos mostrados.

---

## 13.4. Cantidad de elementos

La navegación no debe contener listas completas potencialmente ilimitadas.

Debe mostrar solamente una cantidad limitada de elementos representativos.

La opción:

```text
Ver todos
```

debe llevar a la página completa de la sección.

---

## 13.5. Overflow

Si la navegación supera la altura disponible de la pantalla:

```css
overflow-y: auto;
```

El desplazamiento interno es una protección estructural.

No debe utilizarse como justificación para insertar listas ilimitadas.

---

## 13.6. Posicionamiento

La navegación permanece visible mediante comportamiento sticky.

---

# 14. Retrato y composición de cabecera

La fotografía no utiliza formato circular.

Forma parte de la composición visual de la cabecera.

---

## 14.1. Estado expandido

Área útil aproximada del retrato:

```text
280px x 280px
```

El retrato ocupa aproximadamente:

```text
31%
```

del ancho visual de la cabecera.

La integración entre retrato y fondo debe hacer que ambos se perciban como una única composición.

---

## 14.2. Estado compacto

Área útil aproximada:

```text
72px x 72px
```

El retrato permanece visible.

---

## 14.3. Regla visual

No utilizar:

```text
avatar circular aislado
```

Utilizar:

```text
retrato rectangular integrado en la cabecera
```

El fondo y el retrato pueden mezclarse visualmente dentro de una única imagen o composición.

---

# 15. Iconos y controles

## 15.1. Iconos

| Uso                   |  Tamaño |
| --------------------- | -------: |
| Navegación principal | `22px` |
| Idioma                | `20px` |
| Tema                  | `20px` |
| Tarjetas / destacados | `18px` |

Los iconos funcionan como apoyo visual.

No sustituyen el texto cuando el significado pueda resultar ambiguo.

---

## 15.2. Selector de idioma

```text
altura             => 48px
ancho              => 104px
padding horizontal => 12px
border-radius      => 0
borde              => 1px
```

Debe permanecer directamente visible.

No debe estar oculto dentro de una sección de configuración.

---

## 15.3. Selector de tema

```text
altura        => 48px
ancho         => 48px
border-radius => 0
borde         => 1px
```

Se ubica inmediatamente junto al selector de idioma.

Debe permitir cambiar directamente entre:

```text
tema claro
tema oscuro
```

---

## 15.4. Botón principal

```text
altura             => 48px
padding horizontal => 24px
font-size          => 16px
font-weight        => 600
border-radius      => 0
```

---

## 15.5. Botón secundario

```text
altura             => 48px
padding horizontal => 24px
borde              => 1px
border-radius      => 0
```

---

# Relación entre tema claro y tema oscuro

Los dos temas deben compartir exactamente:

- estructura;
- tamaños;
- tipografía;
- jerarquía;
- espaciado;
- bordes;
- dimensiones;
- iconografía;
- navegación;
- composición de cabecera.

Solamente deben variar los valores visuales necesarios para adaptar:

- fondos;
- superficies;
- textos;
- bordes;
- sombras;
- rojo;
- verde;
- estados interactivos.

El tema oscuro no debe ser considerado un diseño independiente.

Es una representación oscura de la misma identidad visual.

---

# Resumen de tokens principales

## Tipografía

```text
Título => Noto Serif Display / Cormorant Garamond / Georgia / serif
Cuerpo => Inter / Noto Sans / Arial / sans-serif
```

---

## Tema claro

```text
Fondo principal      => #F6F3EE
Superficie primaria  => #FFFFFF
Superficie secundaria=> #F1ECE5
Texto principal      => #141414
Texto secundario     => #5E6167
Rojo principal       => #B51E23
Verde principal      => #2F6D59
Borde                => #D9D3CA
Separador            => #E6E0D8
```

---

## Tema oscuro

```text
Fondo principal      => #0F141B
Superficie primaria  => #141B24
Superficie secundaria=> #18212C
Texto principal      => #F2F1EE
Texto secundario     => #B8BDC6
Rojo principal       => #D6363B
Verde principal      => #58B28D
Borde                => #2A3340
Separador            => #202936
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

---

## Layout de escritorio

```text
Navegación       => 224px
Contenido        => 1fr
Exposición       => 320px
Gap principal    => 24px
Máximo total     => 1504px
```

---

## Cabecera

```text
Expandida => 320px
Compacta  => 112px
Retrato expandido => 280px x 280px
Retrato compacto  => 72px x 72px
```

---

## Controles

```text
Altura estándar => 48px
Icono navegación => 22px
Icono controles  => 20px
Border radius    => 0
```

---

# Estado de la especificación

Los siguientes elementos de identidad visual quedan definidos:

1. tipografía concreta;
2. escala tipográfica;
3. alturas de línea;
4. pesos tipográficos;
5. paleta del tema claro;
6. paleta del tema oscuro;
7. estados visuales;
8. sombras;
9. bordes;
10. espaciado;
11. proporciones del layout;
12. cabecera expandida y compacta;
13. navegación;
14. retrato y composición de cabecera;
15. iconos y controles.

Esta especificación constituye la referencia base de identidad visual para las siguientes etapas de diseño e implementación de `sitio`.
