# 15. Tarjetas

Las diferentes páginas reutilizan un mismo lenguaje visual de tarjetas.

Esto no significa que todos los tipos de tarjeta compartan los mismos datos, sino que compartan lo mismo estilo visual.

Conceptualmente:

```text
---------------------------------
| zona visual                   |
| ----------------------------- |
| contenido propio del elemento |
|                               |
| enlace, cuando corresponda    |
---------------------------------
```

El lenguaje visual común comprende:

```text
Tratamiento de superficies
Bordes
Ausencia de redondeo por defecto
Tipografía
Espaciado
Jerarquía
Tratamiento de imágenes e iconos
Tratamiento de enlaces
Comportamiento entre temas
```

Cada recurso mantiene su propia información.

Conceptualmente:

```text
Contacto
=> icono
=> tipo
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
=> publicación
=> actualización
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

Las tarjetas completas no constituyen implícitamente enlaces cuando existe una acción o un enlace explícito dentro de ellas.

Las rejillas presentan tantas tarjetas completas como permita el ancho disponible.

Cuando una tarjeta adicional ya no debe presentarse correctamente en la misma fila, continúa en la fila siguiente.

La cantidad de columnas resulta del espacio disponible y no de un número fijo establecido para cada página o dispositivo.

