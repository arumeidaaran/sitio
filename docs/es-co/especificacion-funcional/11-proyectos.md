# 11. Proyectos

Volver al índice [aquí](../README.md#índice).

La página de Proyectos utiliza una rejilla de tarjetas.

Conceptualmente:

```text
+-------------+ +-------------+ +-------------+
| proyecto    | | proyecto    | | proyecto    |
+-------------+ +-------------+ +-------------+

+-------------+ +-------------+ +-------------+
| proyecto    | | proyecto    | | proyecto    |
+-------------+ +-------------+ +-------------+
```

Las tarjetas se distribuyen de acuerdo con el espacio disponible y continúan en filas sucesivas cuando sea necesario.

La cantidad de tarjetas por fila no se establece previamente.

Cada tarjeta presenta:

```text
Imagen
Nombre
Descripción breve
Ver proyecto
```

La tarjeta constituye una representación resumida y una invitación a acceder al detalle.

No presenta los lenguajes ni sus porcentajes.

Al seleccionar `Ver proyecto`, toda la región `Contenido` pasa a representar el proyecto seleccionado.

El detalle presenta los datos completos necesarios para el proyecto, incluidos:

```text
Nombre
Imagen
Descripción
Lenguajes
Porcentajes de cada lenguaje
Repositorio
```

Los datos obtenidos desde GitHub son procesados mediante `sitio-api`.

El frontend no consulta GitHub directamente.

Conceptualmente:

```text
sitio
   |
   V
sitio-api
   |
   +-- contenido localizado
   |
   +-- GitHub REST API
```

Los datos localizables, como la descripción, son proporcionados por `sitio-api` de acuerdo con el idioma solicitado.

Los datos que no dependen del idioma deben proceder de GitHub mediante `sitio-api`.

Los porcentajes de lenguajes se calculan a partir de los datos obtenidos desde GitHub.

Su contenido viene del backend.

El orden del listado de proyectos constituye una decisión editorial y no depende automáticamente de la última actualización técnica del repositorio.

Volver al índice [aquí](../README.md#índice).
