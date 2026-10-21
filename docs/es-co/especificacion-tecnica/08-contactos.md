# 08. Contactos

Volver al índice [aquí](../README.md#índice-1).

La página de Contactos combina:

```text
Medios de contacto
Formulario de contacto
```

dentro de la misma región `Contenido`.

---

## Medios de contacto

Los medios de contacto utilizan tarjetas compatibles con el lenguaje visual general del sitio.

Conceptualmente:

```text
--------------------------------
| icono                        |
| ---------------------------- |
| nombre del medio             |
| enlace del medio             |
--------------------------------
```

La tarjeta contiene:

```text
Icono
Tipo de medio
Enlace
```

El icono debe utilizar el mapeo definido en [Contactos](./15-iconos-y-controles.md#contactos).

Las tarjetas de Contactos no utilizan imágenes de contenido como representación del medio.

El propio enlace del medio es un vínculo que lleva hacia el medio directamente.

Cada enlace constituye un objetivo interactivo independiente y dispone como mínimo de un área interactiva de:

```text
48px x 48px CSS
```

La tarjeta completa no se convierte en un segundo objetivo interactivo si la acción ya corresponde al enlace explícito.

---

## Rejilla de contactos

Las tarjetas se organizan horizontalmente mientras exista espacio disponible.

La cantidad de columnas depende del ancho disponible.

Cuando una nueva tarjeta ya no cabe correctamente en la fila actual, sigue en la siguiente.

Los medios presentes dependen de los datos disponibles.

No se define un número fijo de tarjetas por fila.

El crecimiento del texto debe reducir naturalmente la cantidad de tarjetas que caben en una fila antes de recortar el contenido de una tarjeta.

---

## Formulario

El formulario aparece después de los medios de contacto.

Contiene:

```text
Nombre
Apellido
Dirección de correo electrónico
Motivo del contacto
Mensaje
```

Conceptualmente:

```text
--------------------------------------
| Nombre                             |
| ---------------------------------- |
| |                                | |
| ---------------------------------- |
|                                    |
| Apellido                           |
| ---------------------------------- |
| |                                | |
| ---------------------------------- |
|                                    |
| Dirección de correo electrónico    |
| ---------------------------------- |
| |                                | |
| ---------------------------------- |
|                                    |
| Motivo del contacto                |
| ---------------------------------- |
| |                                | |
| ---------------------------------- |
|                                    |
| Mensaje                            |
| ---------------------------------- |
| |                                | |
| |                                | |
| |                                | |
| |                                | |
| ---------------------------------- |
|                                    |
| Enviar                             |
--------------------------------------
```

Todos los campos son obligatorios.

`Mensaje` utiliza un campo de varias líneas.

`Motivo del contacto` utiliza un campo de una línea.

Los campos de una línea utilizan como mínimo:

```text
altura => 48px
```

El campo de varias líneas utiliza una altura superior a ese mínimo de acuerdo con su función.

Todos los campos conservan un área interactiva mínima compatible con:

```text
48px x 48px CSS
```

El control de envío utiliza el tratamiento definido para los botones principales.

Conceptualmente:

```text
first_name
=> 1..100 caracteres

last_name
=> 1..100 caracteres

email
=> dirección válida
=> máximo 254 caracteres

subject
=> 1..200 caracteres

message
=> 1..10000 caracteres
```

---

## Integración visual

El formulario no debe parecer un elemento perteneciente a otro sistema.

Debe utilizar:

```text
tipografía del sitio
bordes del sitio
superficies del tema activo
colores interactivos
espaciado base
foco visible
botón principal
```

Los mecanismos técnicos de validación, envío y protección no cambian la identidad visual general de la página.

---

## Adaptación responsive

Los campos permanecen verticales y utilizan todo el ancho disponible de la región del formulario.

No se reorganizan horizontalmente en escritorio.

El botón principal utiliza:

```text
ancho >= 1024px
=> ancho natural
=> altura mínima 48px
=> padding horizontal 24px
```

Cuando:

```text
ancho < 1024px
```

utiliza:

```text
ancho         => 100%
altura mínima => 48px
```

La misma regla se aplica durante `enviando...`.

La adaptación no cambia los estados ni el contenido del formulario.

Los campos, etiquetas, placeholders, mensajes de validación y controles deben crecer o reorganizarse cuando el redimensionamiento o el espaciado del texto requieren más espacio.

La capacidad de interacción mediante tacto, ratón o lápiz no cambia entre las composiciones responsive.

---

## Estados del formulario de contacto

Los estados del formulario se representan dentro de la propia página de Contactos.

No sustituyen la navegación ni las demás regiones del sitio.

Los valores introducidos se conservan siempre que el resultado de la operación permita o requiera una nueva tentativa.

---

### Estado normal

El control presenta:

```text
Enviar
```

Los campos permanecen disponibles para edición.

---

### Envío en curso

Después de activar `Enviar`, el formulario permanece visible.

Los valores introducidos permanecen presentes.

Durante la operación:

```text
Campos
=> conservan valores
=> temporalmente no cambiables
=> siguen disponibles para el recorrido de foco

Botón
=> enviando...
=> no permite iniciar un segundo envío simultáneo
=> sigue disponible para el recorrido de foco
```

No se utiliza:

```text
skeleton
overlay de página completa
spinner global
```

para representar esta operación.

La navegación permanece disponible.

El inicio del envío no desplaza el foco.

Cuando la operación se inicia desde el botón de envío, el foco permanece en ese control.

Cuando el envío se inicia mediante teclado desde otro campo, el foco permanece en ese campo.

Mientras la operación sigue pendiente, cualquier nueva tentativa de envío por el host debe ser ignorada por el backend antes de generar una segunda solicitud, independientemente de si procede de una activación del botón o de otra forma de envío del formulario.

Cuando la operación termina, los campos vuelven a quedar disponibles para edición y el control vuelve a:

```text
enviar
```

independientemente del resultado recibido.

El frontend no conserva una condición local que impida futuros intentos basándose en una respuesta anterior del backend.

El ancho del botón durante el envío conserva las reglas responsive definidas para el estado normal.

El tamaño y el espaciado del texto durante este estado deben seguir las mismas reglas de crecimiento del control que en el estado normal.

La interacción mediante puntero conserva la misma semántica de activación que el estado normal.

La indisponibilidad temporal durante el envío no introduce una activación diferente basada en presión, gesto o dispositivo.

La semántica accesible concreta de este estado se define en [Mensajes generales del formulario](./24-accesibilidad.md#mensajes-generales-del-formulario).

---

### Envío satisfactorio

Cuando la interfaz recibe el resultado correspondiente a una solicitud aceptada:

```text
Mensaje enviado correctamente.
```

El mensaje utiliza el color semántico de éxito del tema activo.

Después del resultado satisfactorio:

```text
Campos
=> vacíos
=> disponibles

Botón
=> Enviar
```

No se añade una segunda frase de confirmación.

No se incorpora:

```text
Aceptar
Cerrar
Enviar otro
```

como acción adicional.

El formulario permanece en la página y debe volver a utilizarse.

---

### Validación

Los errores de validación se representan junto al campo correspondiente.

Los valores introducidos permanecen en el formulario.

El campo afectado utiliza el tratamiento de error definido por la identidad visual.

El mensaje debe indicar la condición concreta que necesita corrección.

Ejemplos:

```text
Este campo es obligatorio.
```

```text
Introduzca una dirección de correo electrónico válida.
```

```text
El nombre no debe superar los 100 caracteres.
```

```text
El apellido no debe superar los 100 caracteres.
```

```text
El motivo no debe superar los 200 caracteres.
```

```text
El mensaje no debe superar los 10000 caracteres.
```

La validación no depende únicamente de un mensaje general equivalente a:

```text
El formulario contiene errores.
```

El usuario debe identificar qué campo requiere cambio.

Cuando la validación del frontend determina que los datos todavía no cumplen el contrato, no se realiza la solicitud.

Una validación equivalente informada por el backend utiliza la misma representación visible cuando corresponde a un campo concreto.

Después de corregir los valores:

```text
Enviar
```

permanece disponible para una nueva tentativa.

---

### Honeypot

El honeypot forma parte de la protección del formulario pero no introduce una interacción visible adicional.

Su implementación concreta no forma parte de esta especificación visual.

Cuando el mecanismo se activa, no se presenta un estado específico que permita distinguir visualmente ese caso de una solicitud aceptada.

Conceptualmente:

```text
Solicitud aceptada para la interfaz
=> Mensaje enviado correctamente.

Honeypot activado
=> misma representación visible
```

La activación del mecanismo no debe revelar visualmente qué condición interna fue detectada.

---

### Límite de envíos

El límite definido para el formulario es:

```text
5 envíos por IP por hora
```

Cuando el backend informa que el límite se encuentra activo, el formulario conserva los valores introducidos.

El aviso utiliza el color semántico de advertencia del tema activo.

Texto:

```text
Se alcanzó el límite de 5 envíos por hora.

Inténtelo de nuevo más tarde.
```

Después de la respuesta:

```text
Botón
=> Enviar
```

permanece disponible.

El frontend no mantiene:

```text
contador de envíos
temporizador
cuenta regresiva
bloqueo local permanente del botón
estado local equivalente al límite del backend
```

Cada nueva activación de `Enviar` genera una nueva solicitud.

Corresponde al backend determinar en ese momento si la solicitud debe continuar o si el límite sigue vigente.

---

### Fallo de envío

Cuando los datos son válidos pero la operación no debe completarse:

```text
No fue posible enviar el mensaje.

Inténtelo de nuevo.
```

El aviso utiliza el color semántico de error del tema activo.

Los valores introducidos permanecen en el formulario.

Conceptualmente:

```text
Campos
=> conservan valores
=> disponibles nuevamente

Botón
=> Enviar
```

No se vacían los campos.

No se actualiza automáticamente la página.

No se sustituye la página completa por el error.

La interfaz no necesita distinguir visualmente entre causas técnicas que producen el mismo resultado para el usuario.

No se presentan directamente mensajes equivalentes a:

```text
500 Internal Server Error
NetworkError
Microsoft Graph no disponible
Excepción interna
```

---

Volver al índice [aquí](../README.md#índice-1).
