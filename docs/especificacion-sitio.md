# Especificación técnica de identidad visual

## Estado

Esta especificación define la identidad visual base del frontend de `sitio`.

La especificación fue derivada de las decisiones de diseño tomadas durante la definición visual del proyecto y de las representaciones finales aprobadas para los temas claro y oscuro.

Su objetivo es servir como referencia técnica durante la implementación con Angular y Tailwind CSS y durante las etapas posteriores de adaptación a diferentes tamaños de pantalla.

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

El tema claro y el tema oscuro mantienen la misma identidad, estructura, contenido, jerarquía y disposición.

El cambio de tema solamente modifica la representación visual correspondiente a cada paleta.

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

## 2.2. Pantallas pequeñas

| Elemento         | Tamaño |
| ---------------- | -----: |
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
| Padding general de la aplicación       |  `24px` |
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

### Área de exposición de Inicio

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

## 11.2. Inicio

Inicio utiliza tres regiones horizontales:

```text
| navegación | contenido principal | área de exposición |
|   224px     |        1fr          |       320px        |
```

El contenido principal reúne las secciones de contenido destacado.

El área de exposición reúne la actividad reciente.

---

## 11.3. Páginas internas

Las páginas internas no utilizan el área de exposición.

```text
| navegación  | contenido |
|   224px     |    1fr    |
```

La región `Contenido` ocupa todo el espacio restante disponible después de la navegación y cabecera.

La composición interna de esta región cambia de acuerdo con la página representada.

---

## 11.4. Pie

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

## 12.1. Estado expandido

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

## 12.2. Estado compacto

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

# 13. Navegación

## 13.1. Dimensiones

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

---

## 13.2. Estructura

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

## 13.7. Estado activo

Los accesos directos se marcan como activos en su propia página.

Las secciones que contienen elementos permanecen activas tanto en su listado como en sus páginas individuales.

Cuando se representa el detalle de un elemento, el elemento seleccionado también debe disponer de estado activo dentro de la sección expandida.

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

# 14. Foto y composición de cabecera

La fotografía no utiliza formato circular.

Forma parte de `Fondo visual y foto juntos`.

---

## 14.1. Estado expandido

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

## 14.2. Estado compacto

Área visual aproximada correspondiente a la fotografía:

```text
72px x 72px
```

La fotografía permanece visible.

---

## 14.3. Regla visual

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

| Función                     | Icono concreto       |
| --------------------------- | -------------------- |
| Selector de idioma          | `IconWorld`          |
| Desplegar selector          | `IconChevronDown`    |
| Expandir sección            | `IconChevronDown`    |
| Contraer sección            | `IconChevronUp`      |
| Activar tema claro          | `IconSun`            |
| Activar tema oscuro         | `IconMoon`           |

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

| Elemento          | Icono concreto |
| ----------------- | -------------- |
| Inicio            | `IconHome`     |
| Sobre mí          | `IconUser`     |
| Contactos         | `IconMail`     |
| Certificaciones   | `IconAward`    |
| Proyectos         | `IconFolder`   |
| Artículos         | `IconNotebook` |

El mismo mapeo debe mantenerse en los temas claro y oscuro.

El cambio de tema no sustituye un icono por otro para representar una misma sección.

---

## 15.5. Tipos de contenido y acciones

| Elemento o acción        | Icono concreto    |
| ------------------------ | ----------------- |
| Proyecto                 | `IconFolder`      |
| Artículo                 | `IconFileText`    |
| Certificado              | `IconCertificate` |
| Certificación            | `IconAward`       |
| Acceso explícito         | `IconArrowRight`  |

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

| Identificador técnico       | Categoría representada                 | Icono concreto           |
| --------------------------- | -------------------------------------- | ------------------------ |
| `technology`                | Tecnología                             | `IconDeviceDesktopCode`  |
| `development_automation`    | Desarrollo y automatización            | `IconCode`               |
| `professional_experience`   | Experiencia profesional                | `IconBriefcase`          |
| `education`                 | Formación                              | `IconSchool`             |
| `languages`                 | Idiomas                                | `IconLanguage`           |

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

| Tipo de medio            | Icono concreto        |
| ------------------------ | --------------------- |
| Red profesional          | `IconBrandLinkedin`   |
| Repositorio de código    | `IconBrandGithub`     |
| Sitio web                | `IconWorldWww`        |
| Correo electrónico       | `IconMail`            |
| Teléfono                 | `IconPhone`           |
| Mensajería               | `IconBrandWhatsapp`   |

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

## 15.10. Selector de tema

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

El cambio de tema no modifica la página representada.

Debe conservar:

```text
Contenido
Selección editorial
Cantidad de elementos
Orden
Jerarquía
Navegación
Dimensiones
Espaciado
Disposición
Formato de las tarjetas
Actualizaciones
Iconos
```

Solamente cambia la representación visual correspondiente al tema seleccionado.

---

## 15.11. Botón principal

```text
altura             => 48px
padding horizontal => 24px
font-size          => 16px
font-weight        => 600
border-radius      => 0
```

---

## 15.12. Botón secundario

```text
altura             => 48px
padding horizontal => 24px
borde              => 1px
border-radius      => 0
```

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

El cambio de tema no modifica la estructura interna, el orden, el contenido ni la disposición de estas tarjetas.

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

El contenido principal y el área de exposición tienen funciones visuales distintas.

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

# 17. Páginas internas

Las páginas internas comparten un mismo armazón.

Conceptualmente:

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
Estructura global
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

Conceptualmente:

```text
+-------------+ +-------------+ +-------------+
| contacto    | | contacto    | | contacto    |
+-------------+ +-------------+ +-------------+

+-------------+ +-------------+
| contacto    | | contacto    |
+-------------+ +-------------+
```

Los medios presentes dependen de los datos disponibles.

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

Las páginas de listado utilizan una rejilla de tarjetas.

En la representación de escritorio:

```text
3 tarjetas por fila
```

cuando el ancho disponible permite mantener correctamente las dimensiones y el espaciado establecidos.

Conceptualmente:

```text
+-------------+ +-------------+ +-------------+
| tarjeta     | | tarjeta     | | tarjeta     |
+-------------+ +-------------+ +-------------+

+-------------+ +-------------+ +-------------+
| tarjeta     | | tarjeta     | | tarjeta     |
+-------------+ +-------------+ +-------------+

...
```

La rejilla continúa en nuevas filas mientras existan elementos.

La cantidad total de elementos no constituye una restricción estructural del componente.

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

### Cabecera expandida pendiente

El skeleton respeta aproximadamente:

```text
altura             => 320px
Fondo visual y foto juntos
Nombre
Descripción breve
```

### Cabecera compacta pendiente

Cuando corresponde la geometría compacta, respeta aproximadamente:

```text
altura             => 112px
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

---

# 25. Adaptación a diferentes pantallas

La escala tipográfica para pantallas pequeñas se encuentra definida.

La adaptación estructural completa del layout todavía debe responder a la etapa específica de diseño responsive.

Los valores tipográficos establecidos no determinan por sí solos:

```text
Disposición de la navegación
Distribución de columnas
Comportamiento de la cabecera
Posición del área de exposición
Orden de las regiones
Tratamiento de controles
Cantidad de tarjetas por fila en pantallas menores
```

Estas decisiones deben definirse expresamente antes de considerarse parte cerrada de la especificación responsive.

Hasta entonces, las proporciones documentadas para el layout y las rejillas corresponden principalmente a la representación de escritorio.

---

# Relación entre tema claro y tema oscuro

Los dos temas representan exactamente el mismo sitio.

Deben compartir exactamente:

- estructura;
- contenido;
- selección editorial;
- cantidad de elementos;
- orden de los contenidos;
- tipografía;
- jerarquía;
- espaciado;
- bordes estructurales;
- dimensiones;
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
+-- misma estructura
+-- misma disposición
+-- mismos estados

Tema oscuro
|
+-- misma página
+-- mismo contenido
+-- mismo orden
+-- misma cantidad
+-- misma estructura
+-- misma disposición
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
Cambiar la disposición
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

---

## Layout de escritorio

```text
Navegación    => 224px
Contenido     => 1fr
Exposición    => 320px
Gap principal => 24px
Máximo total  => 1504px
```

---

## Cabecera

```text
Expandida         => 320px
Compacta          => 112px
Foto expandida    => 280px x 280px
Foto compacta     => 72px x 72px
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

## Rejilla de escritorio

```text
Listados
=> 3 tarjetas por fila cuando el ancho disponible lo permite

Continuación
=> nuevas filas
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
11. proporciones del layout de escritorio;
12. cabecera expandida y compacta;
13. navegación;
14. foto y composición de cabecera;
15. biblioteca, mapeo, tamaños y uso de iconos;
16. mapeo de controles globales;
17. mapeo de navegación;
18. mapeo de tipos de contenido y acciones;
19. mapeo de iconos de Sobre mí;
20. mapeo de iconos de Contactos;
21. estructura visual de Inicio;
22. representación de contenido destacado;
23. área de exposición y actualizaciones;
24. estructura general de las páginas internas;
25. región variable de Contenido;
26. composición visual de Sobre mí;
27. composición visual de Contactos;
28. formulario de contacto;
29. lenguaje visual común de tarjetas;
30. rejillas de listados;
31. representación de certificados;
32. representación de certificaciones;
33. listado y detalle de Proyectos;
34. representación del lenguaje principal de los proyectos;
35. listado y detalle de Artículos;
36. representación de fechas de Artículos;
37. representación de contenido Markdown;
38. equivalencia estructural y de contenido entre los temas claro y oscuro;
39. representaciones de escritorio de las páginas definidas en los temas claro y oscuro;
40. unidad de presentación y límites de contenido independiente;
41. representación mediante skeleton durante la carga;
42. comportamiento de estados vacíos;
43. comportamiento de errores de carga;
44. tratamiento de elementos visuales obligatorios fallidos;
45. estados de carga y error de elementos subordinados de navegación;
46. estados de carga y error de cabecera;
47. representación de páginas y elementos no encontrados;
48. estado de envío en curso del formulario;
49. confirmación de envío satisfactorio;
50. representación de errores de validación;
51. comportamiento visible del honeypot;
52. representación del límite de envíos;
53. representación de fallos de envío;
54. relación entre estados y colores semánticos;
55. conservación de regiones independientes durante estados parciales.

Los modelos visuales deben utilizar los iconos concretos establecidos en el mapeo de esta especificación.

Las representaciones visuales finales de escritorio constituyen la referencia de composición para las páginas definidas en esta especificación.

Los estados comunes definidos forman parte de la referencia de comportamiento visual para todas las páginas y regiones correspondientes.

La adaptación estructural completa para diferentes tamaños de pantalla permanece pendiente de la etapa correspondiente de diseño responsive.

Esta especificación constituye la referencia base de identidad visual para las siguientes etapas de diseño e implementación de `sitio`.
