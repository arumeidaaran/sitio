# 16. Tipografía y espaciado

Volver al índice [aquí](../README.md#índice-1).

## Tipografía

### Títulos

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

### Cuerpo e interfaz

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

## Escala tipográfica

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

### Escritorio

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

### Pantallas estrechas

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

### Aplicación de la escala

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

## Alturas de línea

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

## Pesos tipográficos

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

## Espaciado

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

### Aplicación

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

## Resumen de tokens principales

### Tipografía

```text
Título => Noto Serif Display / Cormorant Garamond / Georgia / serif
Cuerpo => Inter / Noto Sans / Arial / sans-serif

Raíz
=> font-size: 100%

Texto base
=> 1rem
```

---

### Escalas tipográficas

```text
ancho >= 1024px
=> escala de escritorio

ancho < 1024px
=> escala de pantallas estrechas
```

#### Escritorio

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

#### Pantallas estrechas

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

### Espaciado

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

Volver al índice [aquí](../README.md#índice-1).
