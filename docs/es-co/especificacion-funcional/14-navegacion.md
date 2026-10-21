# 14. Navegación

La estructura principal de navegación permanece disponible independientemente del estado de los elementos subordinados.

Cuando una sección expandida todavía está obteniendo sus elementos subordinados, utiliza skeletons adaptados a la geometría de los accesos de navegación.

Una sección contraída no necesita representar el estado de carga de elementos que no se encuentran visibles.

Si la obtención de los elementos subordinados falla, la sección principal y el acceso al listado completo permanecen disponibles.

El aviso dentro de la navegación utiliza una representación breve equivalente a:

```text
No fue posible cargar los elementos.
```

No se incorpora dentro de la navegación la instrucción de actualizar la página.

Las demás secciones de navegación no son afectadas por la carga o el error de una sección independiente.

## Navegación entre páginas

Después de la resolución inicial, el idioma activo se conserva durante la navegación interna.

El cambio entre páginas no vuelve a consultar ni a cambiar la preferencia almacenada.

Conceptualmente:

```text
Acceso
=> resolver idioma

Navegación interna
=> conservar idioma activo

Nuevo acceso
=> resolver nuevamente

Cambio manual de idioma
=> almacenar nueva preferencia
=> establecer nuevo idioma activo
```

Los enlaces internos son construidos de acuerdo con el idioma activo.

Los segmentos visibles de las direcciones y los `slug` correspondientes a elementos forman parte de la variante localizada.

Un nuevo acceso directo mediante una dirección diferente vuelve a ejecutar la resolución inicial.

Las páginas de detalle mantienen activa la sección a la que pertenece el elemento.

Conceptualmente:

```text
Listado de proyectos
=> Proyectos activo

Proyecto concreto
=> Proyectos activo

Listado de certificaciones
=> Certificaciones activo

Certificado o certificación concreta
=> Certificaciones activo

Listado de artículos
=> Artículos activo

Artículo concreto
=> Artículos activo
```

