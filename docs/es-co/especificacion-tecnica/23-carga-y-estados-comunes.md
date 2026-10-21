# 23. Carga y estados comunes

Volver al índice [aquí](../README.md#índice-1).

## Estados visuales

### Tema claro

#### Enlaces

```text
normal        => #B51E23
hover         => #99181C
visited       => #7C3A65
focus outline => #141414
```

#### Botón principal

```text
fondo normal => #B51E23
fondo hover  => #99181C
texto        => #FFFFFF
```

#### Botón secundario

```text
fondo => #FFFFFF
borde => #7A7E85
texto => #141414
```

#### Navegación activa

```text
fondo           => #F7E9E8
barra izquierda => #B51E23
texto           => #B51E23
```

---

### Tema oscuro

#### Enlaces

```text
normal        => #FE6162
hover         => #FE686A
visited       => #BB7FD3
focus outline => #E2484D
```

#### Botón principal

```text
fondo normal => #D6363B
fondo hover  => #C92F35
texto        => #FFFFFF
```

#### Botón secundario

```text
fondo => transparent
borde => #737B8B
texto => #F2F1EE
```

#### Navegación activa

```text
fondo           => #3A1618
barra izquierda => #D6363B
texto           => #F2F1EE
```

---

### Estados semánticos

#### Tema claro

| Estado      | Color     |
| ----------- | --------- |
| Éxito       | `#2F6D59` |
| Advertencia | `#8F6112` |
| Error       | `#B51E23` |
| Información | `#365E96` |

#### Tema oscuro

| Estado      | Color     |
| ----------- | --------- |
| Éxito       | `#58B28D` |
| Advertencia | `#D6A34A` |
| Error       | `#FE6162` |
| Información | `#6FA8FF` |

---

### Foco

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

## Estados comunes

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

### Unidad de presentación

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

#### Colecciones

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

#### Unidades únicas

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

### Carga

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

#### Colecciones durante la carga

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

### Contenido vacío

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

#### Proyectos

Cuando el listado no contiene proyectos publicados:

```text
No hay proyectos publicados.
```

#### Artículos

Cuando el listado no contiene artículos publicados:

```text
No hay artículos publicados.
```

#### Certificaciones

Cuando el listado no contiene certificados ni certificaciones publicados:

```text
No hay certificaciones publicadas.
```

#### Inicio

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

#### Actualizaciones

Cuando no existen actualizaciones que representar:

```text
No hay actualizaciones recientes.
```

#### Sobre mí

Cuando la carga termina correctamente y no existe información publicada:

```text
No hay información publicada en esta sección.
```

Si el contenido debería existir pero se encuentra incompleto o inválido, se utiliza el estado de error y no el estado vacío.

#### Contactos

Cuando la consulta de medios de contacto termina correctamente sin medios publicados:

```text
Medios de contacto

No hay medios de contacto publicados.

Formulario de contacto

[ formulario ]
```

La ausencia de medios de contacto no elimina el formulario.

#### Elementos individuales

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

### Error de carga

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

#### Colecciones

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

#### Unidades únicas

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

#### Elementos visuales obligatorios

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

### Contenido no encontrado

El estado no encontrado se utiliza cuando la aplicación determina que la dirección o el elemento solicitado no existe.

No se utiliza como sustitución de un error de comunicación o de carga.

La estructura global del sitio permanece visible cuando se encuentra disponible.

No es necesario presentar:

```text
404
```

como elemento visual principal.

#### Página desconocida

Una dirección que no corresponde a una página conocida utiliza:

```text
Página no encontrada

La página que buscas no existe o ya no está disponible.

Volver al inicio
```

`Volver al inicio` constituye una acción normal de navegación.

#### Proyecto

```text
Proyecto no encontrado

El proyecto que buscas no existe o ya no está disponible.

Ver todos los proyectos
```

#### Artículo

```text
Artículo no encontrado

El artículo que buscas no existe o ya no está disponible.

Ver todos los artículos
```

#### Certificado

```text
Certificado no encontrado

El certificado que buscas no existe o ya no está disponible.

Ver todas las certificaciones
```

#### Certificación

```text
Certificación no encontrada

La certificación que buscas no existe o ya no está disponible.

Ver todas las certificaciones
```

Los estados no encontrados no incorporan una indicación de actualizar la página.

Las acciones de navegación de estos estados aplican el tamaño mínimo general de los objetivos interactivos independientes.

---

### Relación entre estados y colores semánticos

Los estados definidos reutilizan los colores semánticos establecidos en [Estados semánticos](#estados-semánticos).

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

### Relación entre estados y estructura

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

Volver al índice [aquí](../README.md#índice-1).
