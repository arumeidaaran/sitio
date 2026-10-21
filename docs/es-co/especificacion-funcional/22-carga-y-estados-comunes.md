# 22. Carga y estados comunes

## Estados comunes

La aplicación representa de forma explícita los estados que afectan a la disponibilidad y a la interacción con el contenido.

Estos estados forman parte de la misma interfaz y conservan:

```text
Cabecera
Navegación
Idioma activo
Tema activo
Identidad visual
```

cuando las regiones correspondientes continúan disponibles.

Un estado técnico interno que no cambia materialmente lo que el usuario debe ver o hacer no requiere una representación visible propia.

### Unidad de contenido

La presentación distingue entre regiones estructurales y unidades de contenido.

Una unidad de contenido constituye la menor entidad que debe comprenderse y utilizarse de forma independiente.

Una unidad solamente se presenta como cargada cuando todos los elementos necesarios para constituirla están disponibles.

Conceptualmente:

```text
Unidad completa
=> presentar contenido

Unidad incompleta
=> no presentar parcialmente
=> em cambio, presentar el estado correspondiente
```

Cuando una colección contiene múltiples unidades independientes, cada unidad debe alcanzar su estado de forma independiente.

Conceptualmente:

```text
Colección
|
+-- unidad completa
|   => presentar
|
+-- unidad completa
|   => presentar
|
+-- unidad incompleta
    => presentar estado de error
```

Una falla en una unidad no invalida las demás unidades completas de la misma colección.

Cuando toda la región representada constituye una única unidad, una falla en cualquiera de sus elementos necesarios afecta a la unidad completa.

Los elementos estructurales de la aplicación no dependen del estado de una unidad de contenido distinta.

### Carga

Las regiones estructurales disponibles permanecen visibles y utilizables mientras se obtiene el contenido.

El contenido pendiente se representa mediante un skeleton que mantiene aproximadamente la geometría de la representación final.

El skeleton utiliza superficies neutrales del tema activo y una franja de luminosidad en gradiente que se desplaza horizontalmente para indicar actividad.

No se utiliza un texto general equivalente a:

```text
Cargando...
```

ni un indicador global que sustituya la página completa.

Conceptualmente:

```text
Estructura disponible
=> permanece visible

Contenido pendiente
=> skeleton

Contenido completo
=> representación final
```

El skeleton solamente representa una operación de carga en curso.

No permanece como representación de un elemento cuya carga ya terminó con error.

En las colecciones, las unidades completas deben sustituir sus representaciones de carga de forma independiente.

Una unidad todavía incompleta no se presenta parcialmente.

### Contenido vacío

Un estado vacío solamente se representa después de finalizar correctamente la carga y determinar que no existe contenido publicable para la región correspondiente.

El estado vacío no utiliza skeleton, tratamiento de error ni una representación visual genérica de contenido.

El mensaje ocupa la región en la que normalmente se representaría el contenido.

En los listados, el texto localizado utiliza una representación equivalente a:

```text
No hay elementos publicados.
```

Las secciones editoriales de Inicio utilizan una representación equivalente a:

```text
No hay elementos destacados.
```

Los accesos hacia los listados completos permanecen disponibles aunque una sección destacada se encuentre vacía.

El área de Actualizaciones utiliza una representación localizada equivalente a:

```text
No hay actualizaciones recientes.
```

Cuando una página de contenido general no dispone de información publicada, utiliza una representación localizada equivalente a:

```text
No hay información publicada en esta sección.
```

Cuando no existen medios de contacto publicados, el estado vacío afecta solamente a esa región.

El formulario de contacto permanece disponible.

Los elementos individuales no utilizan un estado vacío cuando su contrato exige contenido.

Conceptualmente:

```text
Elemento existente y válido
=> presentar

Elemento con datos necesarios incompletos
=> error

Elemento inexistente
=> no encontrado
```

La ausencia válida de un campo opcional no constituye un estado vacío de la unidad.

La navegación no incorpora mensajes de contenido vacío dentro de las secciones que no disponen de elementos subordinados.

### Error de carga

Los errores de carga se representan en la unidad o región cuya información no pudo obtenerse completamente.

Una unidad incompleta no presenta conjuntamente fragmentos válidos y fragmentos fallidos como si constituyeran contenido completo.

En una colección, las unidades completas permanecen disponibles y la unidad fallida conserva su posición mediante el estado de error correspondiente.

Conceptualmente:

```text
Unidad completa
=> contenido

Unidad fallida
=> aviso de error
```

Los avisos de error utilizan textos localizados adecuados al elemento.

Cuando corresponde volver a solicitar el contenido mediante un nuevo acceso, el mensaje utiliza una representación equivalente a:

```text
No fue posible cargar el contenido.

Actualice la página para volver a intentarlo.
```

La aplicación no incorpora una acción automática de reintento para estos estados.

Los elementos visuales necesarios forman parte de la unidad a la que pertenecen.

Si un elemento visual obligatorio no debe cargarse, la unidad no se considera completa.

No se utiliza una imagen genérica de sustitución para presentar una unidad incompleta como si hubiera cargado correctamente.

### Contenido no encontrado

El estado de contenido no encontrado conserva la estructura general del sitio.

Cuando la dirección no corresponde a una página o sección existente, la región de contenido utiliza una representación localizada equivalente a:

```text
Página no encontrada

La página que buscas no existe o ya no está disponible.

Volver al inicio
```

Cuando la estructura de la dirección identifica el tipo de elemento solicitado, el mensaje utiliza ese contexto.

Conceptualmente:

```text
Elemento no encontrado

El elemento que buscas no existe o ya no está disponible.

Ver todos los elementos
```

La acción presentada constituye navegación normal hacia una región existente.

No se utiliza una instrucción de actualización para un elemento que ya fue determinado como inexistente.

