# 05. Estructura de las páginas

## Páginas internas

Las páginas internas comparten un mismo armazón.

En escritorio:

```text
+-------------+----------------------------------------+
|             |              CABECERA                  |
|             |                                        |
|             | Fondo visual y foto juntos +           |
|             | nombre + descripción breve             |
|             +----------------------------------------+
|             |                                        |
|             |                                        |
| NAVEGACIÓN  |              CONTENIDO                 |
|             |                                        |
| Idioma      |                                        |
| Tema        |                                        |
|             |                                        |
| Inicio      |                                        |
| Sobre mí    |                                        |
| Contactos   |                                        |
| Certific.   |                                        |
| Proyectos   |                                        |
| Artículos   |                                        |
|             |                                        |
+-------------+----------------------------------------+
```

Este modelo se aplica a:

```text
Sobre mí
Contactos
Certificaciones
Certificado
Certificación
Proyectos
Proyecto
Artículos
Artículo
```

Y sus derivaciones.

---

### Región Contenido

La región `Contenido` constituye el espacio variable de las páginas internas.

No implica una composición textual única.

debe contener:

```text
Texto
Imágenes
Iconos
Tarjetas
Rejillas
Formularios
Metadatos
Contenido estructurado
Contenido proveniente de Markdown
```

según la página correspondiente.

La variación ocurre dentro de esta región sin cambiar:

```text
Cabecera
Navegación
Estructura global correspondiente al ancho disponible
Idioma activo
Tema activo
```

---

### Listado y detalle

Las secciones que agrupan múltiples elementos utilizan la misma región `Contenido` para su listado y para el elemento individual.

Conceptualmente:

```text
Listado
|
+-- región Contenido
    +-- todos los elementos de la categoría
```

Al seleccionar un elemento:

```text
Detalle
|
+-- región Contenido
    +-- contenido del elemento seleccionado
```

No aparece una nueva región global ni una estructura paralela para el detalle.

---

### Pantallas estrechas

Cuando:

```text
ancho < 1024px
```

las páginas internas utilizan:

```text
Cabecera
Navegación móvil
Contenido
```

como armazón global.

La región `Contenido` utiliza el ancho disponible.

La composición global de una columna no obliga a convertir todos los componentes internos en una única columna.

La regla interna es:

```text
Composición horizontal que cabe correctamente
=> debe mantenerse

Composición horizontal que deja de caber correctamente
=> reorganizar verticalmente
```

La decisión depende del espacio real disponible y de la legibilidad del componente.

El mismo principio se aplica cuando el espacio disponible se reduce por la ampliación del navegador.

---

### Contenido interno ancho

La página completa no debe adquirir desplazamiento horizontal debido a un componente interno.

Cuando un componente supera el espacio disponible, la prioridad es:

```text
1. Reorganizar
2. Redimensionar proporcionalmente
3. Adaptar internamente
4. Utilizar desplazamiento horizontal solamente en el elemento cuando la estructura bidimensional sea necesaria
```

La reorganización se utiliza cuando debe cambiarse la disposición sin perder información o significado.

El redimensionamiento se utiliza para elementos que siguen siendo legibles después de reducirse.

La adaptación interna debe cambiar la representación del componente.

Ejemplos:

```text
Metadatos horizontales
=> disposición vertical
```

```text
Tabla
=> representación adaptada mediante bloques
```

cuando esa transformación conserva correctamente la información.

El desplazamiento horizontal se utiliza solamente cuando las alternativas anteriores perjudican el uso, la comprensión o el significado porque la estructura bidimensional necesita conservarse.

Cuando sea necesario:

```text
Elemento concreto
=> overflow horizontal
```

No:

```text
Página completa
=> overflow horizontal
```

La pertenencia a una categoría concreta, como tabla, código o diagrama, no constituye por sí sola una excepción al reflujo.

El desplazamiento propio utiliza el mecanismo normal proporcionado por el navegador y no depende de una implementación personalizada que requiera arrastrar un elemento de interfaz.

---

