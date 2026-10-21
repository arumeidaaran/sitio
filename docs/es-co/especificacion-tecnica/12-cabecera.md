# 12. Cabecera

La cabecera es una única composición visual.

Incluye:

- Fondo visual y foto juntos;
- nombre;
- descripción breve.

`Fondo visual y foto juntos` no debe volver a dividirse visualmente en un fondo y una fotografía tratados como elementos independientes.

Las representaciones de la cabecera no deben incorporar frases de efecto, lemas, citas ni otros textos adicionales que no formen parte del contenido definido.

---

## Estado expandido en escritorio

Cuando:

```text
ancho >= 1024px
```

utiliza:

```text
altura mínima       => 320px
padding horizontal  => 32px
padding vertical    => 24px
```

Debe mostrar:

- Fondo visual y foto juntos;
- nombre;
- descripción breve.

`320px` constituye la dimensión normal mínima.

La cabecera debe aumentar su altura cuando el tamaño efectivo o el espaciado del texto requieren más espacio para mantener completamente visibles el nombre y la descripción breve.

---

## Estado compacto en escritorio

Cuando:

```text
ancho >= 1024px
```

utiliza:

```text
altura mínima       => 112px
padding horizontal  => 24px
padding vertical    => 16px
```

Debe mantener:

- Fondo visual y foto juntos;
- nombre.

Debe ocultar:

- descripción breve.

`112px` constituye la dimensión normal mínima.

La cabecera debe aumentar su altura cuando el nombre requiere más espacio después del redimensionamiento o cambiación del espaciado textual.

---

## Comportamiento

Al desplazarse la página:

```text
cabecera expandida
        |
        V
cabecera compacta
```

La identidad personal nunca desaparece completamente.

---

## Pantallas estrechas

Cuando:

```text
ancho < 1024px
```

la cabecera mantiene la misma identidad y los mismos estados conceptuales.

El estado expandido presenta:

```text
Fondo visual y foto juntos
Nombre
Descripción breve
```

El estado compacto presenta:

```text
Fondo visual y foto juntos
Nombre
```

La descripción breve deja de mostrarse en el estado compacto.

La cabecera no utiliza alturas máximas rígidas.

Su altura deriva de:

```text
Contenido
Padding
Ancho disponible
Tamaño efectivo del texto
Espaciado efectivo del texto
```

La fotografía permanece integrada en `Fondo visual y foto juntos`.

No se convierte en un avatar circular.

No desaparece completamente en el estado compacto.

---

## Contraste de la cabecera en el tema oscuro

El nombre y la descripción breve utilizan:

```text
#F2F1EE
```

cuando se representan sobre el fondo visual de la cabecera.

La región situada detrás del bloque textual utiliza una capa negra con:

```text
rgba(0, 0, 0, 0.60)
```

como opacidad mínima efectiva.

La capa cubre completamente la zona ocupada por el texto.

debe degradarse hacia una opacidad menor o hacia transparencia fuera de esa región.

No debe reducirse dentro del área ocupada por el nombre o por la descripción breve.

Conceptualmente:

```text
Fotografía
        |
        V
Capa negra >= 60%
        |
        V
Texto #F2F1EE
```

La garantía se calcula suponiendo el caso más luminoso posible detrás del texto.

Un fondo original:

```text
#FFFFFF
```

después de una capa negra al `60%` produce como peor fondo efectivo:

```text
#666666
```

El contraste resultante es:

```text
#F2F1EE sobre #666666
=> 5.0834876786:1
```

El resultado supera:

```text
4.5:1
```

y permite que tanto el nombre como la descripción breve satisfagan AA sin depender de que el texto pueda considerarse grande.

La regla se conserva en cualquier composición donde el texto permanezca superpuesto a la fotografía.

La sustitución futura de la fotografía no cambia esta garantía mientras permanezcan el color del texto y la capa mínima establecida.

Cuando el bloque textual aumenta debido al redimensionamiento o al espaciado del texto, la región cubierta por la capa debe aumentar junto con él.

---

## Foto y composición de cabecera

La fotografía no utiliza formato circular.

Forma parte de `Fondo visual y foto juntos`.

---

### Estado expandido de escritorio

Área visual aproximada correspondiente a la fotografía:

```text
280px x 280px
```

La fotografía ocupa aproximadamente:

```text
31%
```

del ancho visual de la cabecera.

El crecimiento vertical de la cabecera provocado por el texto no exige aumentar proporcionalmente esta fotografía.

---

### Estado compacto de escritorio

Área visual aproximada correspondiente a la fotografía:

```text
72px x 72px
```

La fotografía permanece visible.

El crecimiento vertical necesario para acomodar el nombre no cambia automáticamente esta dimensión.

---

### Pantallas estrechas

Por debajo de:

```text
1024px
```

la fotografía sigue integrada en `Fondo visual y foto juntos`.

Debe adaptarse proporcionalmente al ancho disponible y a la geometría resultante de la cabecera.

La fotografía permanece presente tanto en el estado expandido como en el compacto y su comportamiento permanece lo mismo al comportamiento del escritorio.

---

### Regla visual

No utilizar:

```text
avatar circular aislado
```

La fotografía debe permanecer integrada en `Fondo visual y foto juntos`.

---

## Estados de la cabecera

La cabecera constituye una unidad única.

Durante su carga mantiene el espacio estructural correspondiente y utiliza skeleton adaptado a su composición.

### Cabecera expandida pendiente en escritorio

El skeleton respeta aproximadamente:

```text
altura mínima       => 320px
Fondo visual y foto juntos
Nombre
Descripción breve
```

La geometría efectiva debe acompañar el crecimiento que correspondería al contenido textual con el tamaño y espaciado activos.

### Cabecera compacta pendiente en escritorio

Cuando corresponde la geometría compacta, respeta aproximadamente:

```text
altura mínima       => 112px
Fondo visual y foto juntos
Nombre
```

La geometría efectiva debe acompañar el crecimiento que correspondería al nombre con el tamaño y espaciado activos.

### Pantallas estrechas

Cuando:

```text
ancho < 1024px
```

el skeleton no utiliza una altura máxima rígida.

Respeta aproximadamente la geometría responsive resultante del contenido, el padding, el ancho disponible, el tamaño del texto y su espaciado.

En estado expandido representa:

```text
Fondo visual y foto juntos
Nombre
Descripción breve
```

En estado compacto representa:

```text
Fondo visual y foto juntos
Nombre
```

La cabecera no se presenta parcialmente.

Si una parte obligatoria todavía se encuentra pendiente, la unidad sigue en estado de carga.

### Error

Cuando la cabecera no debe constituirse completamente:

```text
No fue posible cargar la información de la cabecera.

Actualice la página para volver a intentarlo.
```

La región de cabecera presenta el aviso dentro del espacio correspondiente.

Una falla de la cabecera no elimina la navegación ni invalida las regiones de contenido que puedan continuar funcionando.

---

## Resumen de dimensiones

```text
Escritorio expandida => min-height 320px
Escritorio compacta  => min-height 112px
Foto expandida       => 280px x 280px
Foto compacta        => 72px x 72px
Pantallas estrechas  => altura derivada del contenido
```

---

