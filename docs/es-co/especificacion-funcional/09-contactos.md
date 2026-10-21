# 09. Contactos

Volver al índice [aquí](../README.md#índice).

La página de Contactos combina dos mecanismos:

```text
Contactos
|
+-- Medios de contacto
|
+-- Formulario de contacto
```

## Medios de contacto

Los medios existentes se presentan mediante tarjetas que reutilizan el lenguaje visual general del sitio.

Conceptualmente:

```text
--------------------------------
| icono                        |
| ---------------------------- |
| tipo de contacto             |
| enlace                       |
--------------------------------
```

Cada medio utiliza el icono correspondiente a su tipo.

Las tarjetas de Contactos no utilizan imágenes de contenido como representación del medio.

El texto correspondiente al medio identifica la tarjeta.

El propio valor representado funciona como enlace cuando corresponde.

No se incorpora un segundo enlace redundante como:

```text
Ver perfil
```

cuando el propio medio ya permite realizar la navegación.

Los diferentes tipos de contacto deben incluir:

```text
LinkedIn
GitHub
Sitio web
Correo electrónico
WhatsApp
```

## Formulario de contacto

El formulario permite enviar un mensaje directamente desde el sitio.

Contiene:

```text
Nombre
Apellido
Dirección de correo electrónico
Motivo del contacto
Mensaje
```

`Nombre` y `Apellido` se mantienen como campos separados.

El nombre proporcionado debe ser utilizado posteriormente para dirigirse a la persona durante una respuesta.

Conceptualmente:

```text
Motivo del contacto
=> asunto del correo

Mensaje
=> cuerpo principal del correo
```

La dirección de correo proporcionada permite responder posteriormente al remitente.

El frontend no contiene credenciales de correo ni se comunica directamente con el servicio utilizado para realizar el envío.

Conceptualmente:

```text
Usuario
   |
   V
Formulario
   |
   V
frontend
   |
   V
backend
   |
   V
Microsoft Graph
   |
   V
Correo
```

La página visible continúa perteneciendo a la ruta localizada del sitio:

```text
/{idioma}/{contactos-localizado}/
```

La API utiliza una misma ruta para consultar los medios y enviar el formulario, diferenciando la operación mediante el método HTTP:

```http
GET /api/v1/{idioma}/contacts/
```

```text
=> obtiene los medios de contacto
```

```http
POST /api/v1/{idioma}/contacts/
```

```text
=> recibe y procesa el formulario de contacto
```

Los contactos pertenecen al recurso `contacts`.

No forman parte del contrato de `profile`.

## Protección del formulario

El formulario utiliza protección proporcional al contexto de un sitio personal.

Se utilizan:

```text
Validación mediante Pydantic
Límites de longitud
Honeypot
Límite de 5 envíos por IP por hora
```

No se incorpora CAPTCHA.

La validación mediante Pydantic garantiza que los datos recibidos cumplen el contrato antes de ser procesados.

Los límites de longitud evitan entradas descontroladas.

El honeypot permite detectar envíos automatizados simples sin introducir una interacción adicional para el usuario.

La limitación por IP reduce el abuso repetitivo del endpoint antes de que la solicitud llegue al servicio utilizado para enviar el correo.

La aceptación de la solicitud por `sitio-api` se representa mediante una respuesta HTTP `202 Accepted`.

## Estados del formulario de contacto

El formulario conserva sus valores mientras una operación de envío se encuentra en curso o termina con un resultado que permite una nueva tentativa.

Durante el envío:

```text
Formulario
=> permanece visible
=> conserva los valores
=> comunica que la operación está en curso

Campos
=> conservan los valores
=> temporalmente no cambiables
=> continúan disponibles para el recorrido de foco

Enviar
=> enviando...
=> temporalmente no disponible para una nueva activación
=> continúa disponible para el recorrido de foco
```

Una nueva activación del envío no inicia una segunda solicitud mientras la operación actual continúa pendiente.

La navegación y las demás regiones disponibles permanecen utilizables.

El inicio del envío se comunica también de forma no interruptiva a las tecnologías de asistencia.

Esta comunicación no introduce un segundo mensaje visible que repita innecesariamente el texto ya mostrado por el control de envío.

La información accesible sobre el progreso se mantiene separada de la región que está siendo procesada para que pueda comunicarse mientras la operación continúa.

El inicio del envío no desplaza automáticamente el foco.

Cuando la acción fue iniciada desde el control de envío, el foco permanece en ese control durante la operación.

Cuando el envío fue iniciado desde otro control del formulario mediante teclado, el foco permanece en el control desde el que se realizó la acción.

Cuando la operación termina:

```text
Formulario
=> deja de comunicar una operación en curso

Campos
=> vuelven a estar disponibles para cambio

"Enviando..." 
=> Regresa a "enviar"

Control de envío
=> vuelve a estar disponible
```

Después se representa el resultado correspondiente.

No se incorpora un aviso adicional equivalente a:

```text
Envío terminado.
```

porque el propio resultado informa qué ocurrió.

El frontend no mantiene un estado persistente que determine si una nueva solicitud será aceptada por los mecanismos de protección del backend.

### Envío satisfactorio

Cuando la solicitud es aceptada como un envío satisfactorio para la interfaz:

```text
Mensaje enviado correctamente.
```

Los campos se vacían y vuelven a quedar disponibles.

No se incorpora una segunda frase de confirmación ni una acción adicional.

### Validación

Los errores de validación conservan los valores introducidos.

Cada problema se representa junto al campo correspondiente mediante un mensaje localizado que indica la corrección necesaria.

Conceptualmente:

```text
Campo
[ valor ]

Mensaje de validación
```

El formulario no se sustituye por un error general.

El control de envío permanece disponible después de la validación para permitir una nueva solicitud una vez corregidos los campos.

La validación realizada por el backend se representa mediante el mismo tratamiento cuando corresponde a un campo concreto.

### Honeypot

La activación del honeypot no genera un estado visible específico.

El frontend no informa qué condición de protección fue activada ni presenta un mensaje que permita distinguir este caso de una solicitud aceptada normalmente.

La protección depende de que su implementación permanezca secreta.

### Límite de envíos

Cuando el backend informa que se alcanzó el límite de envíos, el formulario conserva todos los valores introducidos.

El aviso utiliza el estado semántico de advertencia y una representación localizada equivalente a:

```text
Se alcanzó el límite de 5 envíos por hora.

Inténtelo de nuevo más tarde.
```

El control permanece disponible como:

```text
Enviar
```

Cada nueva tentativa constituye una nueva solicitud y corresponde al backend determinar si el límite continúa vigente.

El frontend no mantiene contadores, temporizadores ni una condición local equivalente al límite aplicado por el servidor.

### Fallo de envío

Cuando una solicitud válida no debe completar la operación de envío, el formulario conserva todos los valores introducidos.

El aviso utiliza el estado semántico de error y una representación localizada equivalente a:

```text
No fue posible enviar el mensaje.

Inténtelo de nuevo.
```

El control vuelve a:

```text
Enviar
```

No se actualiza automáticamente la página, no se vacían los campos y no se sustituye la página completa por el error.

Volver al índice [aquí](../README.md#índice).
