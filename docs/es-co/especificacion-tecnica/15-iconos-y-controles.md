# 15. Iconos y controles

Volver al índice [aquí](../README.md#índice-1).

## Biblioteca de iconos

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

## Mapeo de iconos

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

## Controles globales

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

## Navegación principal

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

## Tipos de contenido y acciones

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

## Sobre mí

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

## Contactos

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

## Tamaños

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

## Selector de idioma

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

## Selector de tema

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

El icono interior debe mantener el tamaño definido en [Tamaños](#tamaños).

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

## Botón principal

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

## Botón secundario

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

## Objetivos interactivos

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

Volver al índice [aquí](../README.md#índice-1).
