# 13. Navegación

## Dimensiones de escritorio

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

## Estructura de escritorio

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

## Jerarquía expandible

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

## Cantidad de elementos

La navegación no debe contener listas completas potencialmente ilimitadas.

Debe mostrar solamente una cantidad limitada de elementos representativos.

La cantidad mostrada no constituye una restricción estructural fija.

El componente debe admitir variaciones en la cantidad de elementos sin alterar la estructura general de la navegación.

El acceso al listado completo permite continuar hacia la página correspondiente.

---

## Overflow de escritorio

Si la navegación lateral supera la altura disponible de la pantalla:

```css
overflow-y: auto;
```

El desplazamiento interno es una protección estructural.

No debe utilizarse como justificación para insertar listas ilimitadas.

El crecimiento vertical producido por texto redimensionado o por un mayor espaciado textual debe seguir utilizando este desplazamiento vertical interno cuando la navegación supera la altura visible.

El desplazamiento corresponde al comportamiento normal de la región y no introduce una función personalizada basada en arrastre.

---

## Posicionamiento

La navegación permanece disponible durante el desplazamiento mediante comportamiento sticky.

En escritorio se aplica a la navegación lateral.

En pantallas estrechas se aplica a la composición superior formada por la cabecera compacta y la barra de navegación móvil.

---

## Estado activo

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

## Navegación en pantallas estrechas

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

## Estructura del menú en pantallas estrechas

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

## Navegación desde el menú estrecho

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

Cuando la selección produce una nueva página mediante navegación interna, después de completar el cierre del menú y representar el destino se aplica la gestión de foco definida en [Cambio de página y foco](./24-accesibilidad.md#cambio-de-página-y-foco).

La barra:

```text
Menú | Idioma | Tema
```

sigue disponible durante el desplazamiento junto con la cabecera compacta.

---

## Estados de la navegación

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

