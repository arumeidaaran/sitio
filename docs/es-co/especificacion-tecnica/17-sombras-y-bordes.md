# 17. Sombras y bordes

Volver al índice [aquí](../README.md#índice-1).

## Sombras

Las sombras deben utilizarse para producir profundidad y separación visual.

No deben convertirse en decoración permanente de todos los elementos.

### Tema claro

#### Sombra ligera

```css
box-shadow: 0 4px 12px rgba(17, 17, 17, 0.06);
```

#### Sombra media

```css
box-shadow: 0 8px 24px rgba(17, 17, 17, 0.10);
```

#### Cabecera compacta o elemento sticky

```css
box-shadow: 0 6px 18px rgba(17, 17, 17, 0.12);
```

---

### Tema oscuro

#### Sombra ligera

```css
box-shadow: 0 4px 14px rgba(0, 0, 0, 0.24);
```

#### Sombra media

```css
box-shadow: 0 10px 26px rgba(0, 0, 0, 0.34);
```

#### Cabecera compacta o elemento sticky

```css
box-shadow: 0 8px 24px rgba(0, 0, 0, 0.40);
```

---

### Uso previsto

Las sombras deben utilizarse en:

- paneles;
- navegación sticky;
- cabecera compacta;
- elementos destacados;
- tarjetas;
- controles importantes.

No deben utilizarse de forma indiscriminada en cada bloque de contenido.

---

## Bordes

### Border radius

El valor base es:

```css
border-radius: 0;
```

El redondeo no forma parte de la identidad visual principal.

Si algún elemento concreto requiere un radio por razones funcionales o visuales, deberá definirse expresamente.

---

### Espesores

```text
Borde estándar  => 1px
Separador       => 1px
Línea de acento => 3px
```

---

### Tema claro

```text
Borde         => #7A7E85
Acento rojo   => #B51E23
Acento verde  => #2F6D59
```

El valor `#7A7E85` se utiliza tanto para bordes como para separadores cuando la composición requiere una línea.

---

### Tema oscuro

```text
Borde funcional      => #737B8B
Separador decorativo => #202936
Acento rojo          => #D6363B
Acento verde         => #58B28D
```

`#737B8B` se utiliza en bordes de controles y en cualquier línea necesaria para reconocer un componente, un estado o una separación estructural.

`#202936` solamente debe utilizarse cuando la línea es decorativa y su ausencia no cambia la comprensión ni la identificación de un componente.

---

### Regla visual

No todos los elementos deben estar encerrados en cajas.

La separación entre regiones debe priorizar:

1. espaciado;
2. alineación;
3. cambio de superficie;
4. separadores;
5. bordes solamente cuando aporten información estructural.

---

Volver al índice [aquí](../README.md#índice-1).
