# 06. Estructura de las páginas

Volver al índice [aquí](../README.md#índice).

Las páginas comparten una estructura general común.

```text
Aplicación
|
+-- Cabecera
|   |
|   +-- Fondo visual y foto juntos
|   +-- Nombre
|   +-- Descripción breve
|
+-- Cuerpo
    |
    +-- Navegación
    |   |
    |   +-- Selección de idioma
    |   +-- Selección de tema
    |   +-- Secciones
    |
    +-- Contenido
    |
    +-- Área de exposición
        => solamente en Inicio
```

No existe un pie global.

La cabecera constituye una única composición visual formada por:

```text
Fondo visual y foto juntos
Nombre
Descripción breve
```

Durante el desplazamiento, la cabecera reduce su presencia manteniendo visibles la fotografía y el nombre.

La descripción breve pertenece al estado expandido y no necesita permanecer visible cuando la cabecera se encuentra compactada.

En las composiciones de escritorio, la navegación es vertical y permanece disponible durante el desplazamiento.

En las composiciones estrechas, la navegación se reorganiza para utilizar el espacio horizontal disponible sin mantener una barra lateral reducida artificialmente.

Los controles de idioma y tema aparecen directamente en la navegación.

No se encuentran ocultos dentro de una sección adicional de configuración.

La navegación organiza primero los accesos directos:

```text
Inicio
Sobre mí
Contactos
```

Después presenta las secciones que contienen elementos y representan parte de su jerarquía:

```text
Certificaciones
Proyectos
Artículos
```

Conceptualmente:

```text
Navegación
|
+-- Inicio
+-- Sobre mí
+-- Contactos
|
+-- Certificaciones
|   |
|   +-- certificado o certificación
|   +-- certificado o certificación
|   +-- ...
|   +-- Ver todas las certificaciones
|
+-- Proyectos
|   |
|   +-- Proyecto
|   +-- Proyecto
|   +-- ...
|   +-- Ver todos los proyectos
|
+-- Artículos
    |
    +-- Artículo
    +-- Artículo
    +-- ...
    +-- Ver todos los artículos
```

La navegación no reproduce necesariamente todos los elementos existentes.

Cuando una sección debe crecer indefinidamente, presenta una cantidad limitada de elementos y un acceso explícito a la sección completa.

El acceso al listado completo debe indicar el destino correspondiente.

Conceptualmente:

```text
Ver todos los proyectos

Ver todos los artículos

Ver todas las certificaciones
```

Si la navegación supera el espacio disponible, dispone del comportamiento correspondiente a la composición utilizada.

La región `Contenido` presenta la información correspondiente a la página activa.

En las páginas internas, esta región constituye la parte variable de la estructura general.

Conceptualmente:

```text
Cabecera
=> permanece

Navegación
=> permanece

Contenido
=> cambia según la página
```

La composición interna de `Contenido` depende de la naturaleza de cada página y del espacio disponible.

La navegación interna conserva el contexto lingüístico previamente establecido y utiliza ese mismo idioma para construir el acceso hacia las demás secciones.

## Páginas internas

Las páginas internas utilizan el mismo armazón general.

Conceptualmente:

```text
Página interna
|
+-- Cabecera
|   |
|   +-- Fondo visual y foto juntos
|   +-- Nombre
|   +-- Descripción breve
|
+-- Cuerpo
    |
    +-- Navegación
    |
    +-- Contenido
```

Las páginas internas no utilizan el área de exposición de Inicio.

La región `Contenido` debe adoptar una composición propia según la naturaleza de la página sin cambiar la estructura global del sitio.

Volver al índice [aquí](../README.md#índice).
