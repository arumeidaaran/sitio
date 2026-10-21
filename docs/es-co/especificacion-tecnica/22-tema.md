# 22. Tema

## Paleta del tema claro

### Colores neutrales

| Uso                   | Color     |
| --------------------- | --------- |
| Fondo principal       | `#F6F3EE` |
| Superficie primaria   | `#FFFFFF` |
| Superficie secundaria | `#F1ECE5` |
| Texto principal       | `#141414` |
| Texto secundario      | `#5E6167` |
| Texto tenue           | `#676B72` |
| Borde                 | `#7A7E85` |

El mismo token de borde se utiliza para los bordes estructurales, bordes de controles y separadores cuando una línea resulta necesaria.

---

### Colores de identidad

| Uso                    | Color     |
| ---------------------- | --------- |
| Rojo principal         | `#B51E23` |
| Rojo hover             | `#99181C` |
| Rojo suave / selección | `#F7E9E8` |
| Verde principal        | `#2F6D59` |
| Verde hover            | `#255847` |
| Verde suave            | `#E8F2EE` |

---

### Colores de apoyo

| Uso            | Color     |
| -------------- | --------- |
| Negro de apoyo | `#0E0E0E` |
| Blanco puro    | `#FFFFFF` |

---

## Paleta del tema oscuro

### Colores neutrales

| Uso                   | Color     |
| --------------------- | --------- |
| Fondo principal       | `#0F141B` |
| Superficie primaria   | `#141B24` |
| Superficie secundaria | `#18212C` |
| Texto principal       | `#F2F1EE` |
| Texto secundario      | `#B8BDC6` |
| Texto tenue           | `#8E97A3` |
| Borde funcional       | `#737B8B` |
| Separador decorativo  | `#202936` |

`#737B8B` se utiliza cuando una línea resulta necesaria para reconocer un componente, comprender un estado o proporcionar una separación estructural que necesita ser percibida.

`#202936` se reserva para separadores puramente decorativos cuya presencia no constituye información necesaria.

Un separador que pase a desempeñar una función necesaria debe utilizar el valor de borde funcional.

---

### Colores de identidad

| Uso                          | Color     |
| ---------------------------- | --------- |
| Rojo interactivo             | `#FE6162` |
| Rojo interactivo hover       | `#FE686A` |
| Rojo de fondo principal      | `#D6363B` |
| Rojo de fondo hover          | `#C92F35` |
| Rojo suave / selección       | `#3A1618` |
| Verde principal              | `#58B28D` |
| Verde hover                  | `#4FA683` |
| Verde suave                  | `#173328` |

El rojo utilizado como primer plano y el rojo utilizado como fondo de controles mantienen funciones distintas.

Los valores de primer plano se utilizan cuando el rojo aparece como texto, enlace, icono o información equivalente.

Los valores de fondo se utilizan en componentes rellenos que presentan texto claro sobre la superficie roja.

No debe intercambiarse un valor entre estas funciones sin comprobar nuevamente el contraste resultante.

---

### Colores de apoyo

| Uso           | Color     |
| ------------- | --------- |
| Casi negro    | `#0A0E13` |
| Blanco cálido | `#F7F5F1` |

---

### Colores auxiliares accesibles

| Uso              | Color     |
| ---------------- | --------- |
| Enlace visitado  | `#BB7FD3` |
| Foco             | `#E2484D` |
| Placeholder      | `#8E97A3` |
| Base de skeleton | `#18212C` |

---

## Relación entre tema claro y tema oscuro

Los dos temas representan exactamente el mismo sitio.

Para un mismo ancho disponible deben compartir exactamente:

- estructura;
- contenido;
- selección editorial;
- cantidad de elementos;
- orden de los contenidos;
- tipografía;
- jerarquía;
- espaciado;
- bordes estructurales;
- dimensiones correspondientes a la composición activa;
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
- reglas responsive;
- puntos de ruptura;
- reglas de los estados comunes;
- límites de las unidades de presentación;
- comportamiento de carga, vacío, error y contenido no encontrado;
- comportamiento de los estados del formulario;
- estructura semántica de idioma;
- escala tipográfica relativa;
- reglas de redimensionamiento del texto;
- reglas de reflujo;
- reglas de espaciado del texto;
- comportamiento entre orientaciones;
- tamaños mínimos de objetivos interactivos;
- mecanismos de entrada disponibles;
- comportamiento de activación mediante puntero;
- reglas de interacción mediante tacto;
- ausencia de dependencia funcional de `hover`;
- reglas de cancelación del puntero;
- ausencia de arrastre obligatorio;
- comportamiento de etiquetas visibles y nombres accesibles;
- reglas de pruebas funcionales de accesibilidad;
- porcentaje obligatorio de aprobación de las pruebas automatizadas;
- criterios de comprobación manual aplicables.

Conceptualmente:

```text
Tema claro
|
+-- misma página
+-- mismo contenido
+-- mismo orden
+-- misma cantidad
+-- misma estructura responsive
+-- misma disposición para el mismo ancho
+-- mismos estados
+-- mismas reglas de redimensionamiento y reflujo
+-- mismos objetivos interactivos
+-- mismos mecanismos de entrada
+-- misma interacción funcional
+-- misma estrategia de validación de accesibilidad

Tema oscuro
|
+-- misma página
+-- mismo contenido
+-- mismo orden
+-- misma cantidad
+-- misma estructura responsive
+-- misma disposición para el mismo ancho
+-- mismos estados
+-- mismas reglas de redimensionamiento y reflujo
+-- mismos objetivos interactivos
+-- mismos mecanismos de entrada
+-- misma interacción funcional
+-- misma estrategia de validación de accesibilidad
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
Cambiar la composición responsive
Cambiar los puntos de ruptura
Cambiar los espacios estructurales
Cambiar los textos
Cambiar los iconos
Cambiar los campos mostrados
Cambiar el significado de los estados
Cambiar las reglas de una unidad de presentación
Cambiar las reglas funcionales de accesibilidad
Cambiar la estructura semántica
Cambiar la navegación mediante teclado
Cambiar el idioma semántico del documento
Cambiar el idioma semántico de las partes
Cambiar la escala tipográfica
Cambiar las reglas de redimensionamiento
Cambiar las reglas de reflujo
Cambiar las reglas de espaciado del texto
Cambiar el comportamiento entre orientaciones
Cambiar el tamaño mínimo de los objetivos interactivos
Cambiar los mecanismos de entrada admitidos
Cambiar la activación mediante puntero
Introducir dependencia funcional de hover
Cambiar las reglas de cancelación del puntero
Introducir arrastre obligatorio
Cambiar la relación entre etiqueta visible y nombre accesible
Cambiar el criterio de aceptación automatizada
Eliminar comprobaciones manuales aplicables
```

El tema oscuro no debe ser considerado un diseño independiente.

El tema claro tampoco debe ser considerado una composición alternativa.

Ambos son representaciones visuales de la misma interfaz.

---

## Resumen del tema claro

```text
Fondo principal       => #F6F3EE
Superficie primaria   => #FFFFFF
Superficie secundaria => #F1ECE5

Texto principal       => #141414
Texto secundario      => #5E6167
Texto tenue           => #676B72

Borde                 => #7A7E85

Rojo principal        => #B51E23
Rojo hover            => #99181C
Rojo suave            => #F7E9E8

Verde principal       => #2F6D59
Verde hover           => #255847
Verde suave           => #E8F2EE

Éxito                 => #2F6D59
Advertencia           => #8F6112
Error                 => #B51E23
Información           => #365E96

Focus color           => #141414
Placeholder           => #676B72
```

---

## Resumen del tema oscuro

```text
Fondo principal       => #0F141B
Superficie primaria   => #141B24
Superficie secundaria => #18212C

Texto principal       => #F2F1EE
Texto secundario      => #B8BDC6
Texto tenue           => #8E97A3

Borde funcional       => #737B8B
Separador decorativo  => #202936

Rojo interactivo      => #FE6162
Rojo hover            => #FE686A
Rojo de fondo         => #D6363B
Rojo de fondo hover   => #C92F35
Rojo suave            => #3A1618

Verde principal       => #58B28D
Verde hover           => #4FA683
Verde suave           => #173328

Éxito                 => #58B28D
Advertencia           => #D6A34A
Error                 => #FE6162
Información           => #6FA8FF

Focus color           => #E2484D
Placeholder           => #8E97A3
Enlace visitado       => #BB7FD3

Casi negro            => #0A0E13
Blanco cálido         => #F7F5F1

Skeleton base         => #18212C
```

### Cabecera del tema oscuro

```text
Texto                 => #F2F1EE
Capa negra mínima     => 60%
Peor fondo resultante => #666666
Contraste mínimo      => 5.0834876786:1
```

---

