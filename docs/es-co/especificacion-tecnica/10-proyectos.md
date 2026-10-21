# 10. Proyectos

La página de Proyectos utiliza la rejilla general de tarjetas.

---

## Tarjeta

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

## Detalle

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

## Lenguaje principal

El detalle representa el lenguaje principal del proyecto como información técnica.

Conceptualmente:

```text
Lenguaje principal
=> lenguaje
```

No se requiere representar en el detalle una distribución porcentual de todos los lenguajes del repositorio.

---

## Orden del listado

El orden visual del listado constituye una decisión editorial.

No debe cambiarse automáticamente solamente porque un repositorio haya recibido una actualización técnica reciente.

---

## Adaptación responsive del detalle

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

