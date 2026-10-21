# 17. Validación y pruebas

## Validación

La aplicación utiliza TypeScript en modo estricto para aumentar la validación estática del código.

Los cambios integrados deben verificar el formato, la calidad del código, las pruebas automatizadas y la construcción de producción antes de ser promovidos.

El formato se comprueba mediante las convenciones establecidas para las herramientas del frontend.

El análisis estático verifica el código y las plantillas de la aplicación mediante las reglas configuradas para el proyecto.

Las pruebas unitarias deben terminar correctamente y conservar la cobertura completa exigida para las instrucciones, ramas, funciones y líneas incluidas en la medición.

Las pruebas de navegador verifican los recorridos configurados mediante distintos motores de navegación.

La construcción de producción debe completarse correctamente y utilizar la ruta base correspondiente al despliegue del sitio.

La instalación de dependencias utilizada por las validaciones automatizadas debe reproducir la resolución registrada en el proyecto.

Conceptualmente:

```text
Instalación reproducible
      |
      V
Comprobación de formato
      |
      V
Análisis estático
      |
      V
Pruebas unitarias y cobertura
      |
      V
Pruebas de navegador
      |
      V
Construcción de producción
      |
      V
Validación aprobada
```

La aceptación automatizada exige la aprobación de la totalidad de las pruebas ejecutadas.

Una prueba automatizada fallida, una cobertura insuficiente o una construcción fallida invalida la validación y evita la promoción del cambio.

La ausencia de fallos en la auditoría automática de accesibilidad no constituye por sí sola una declaración completa de conformidad.

Los aspectos cuya evaluación depende de interpretación humana deben conservar además la comprobación manual correspondiente.

Los idiomas utilizados por la interfaz forman parte de la configuración y los elementos propios de `sitio`.

Los contratos de contenido proporcionados por `sitio-api` deben garantizar:

```text
original pertenece a supported
```

La publicación del contenido debe procurar además:

```text
idioma por defecto pertenece a supported
```

Esta segunda condición constituye una regla de publicación y mantenimiento, pero la aplicación permanece preparada para continuar funcionando si se incumple.

Los `slug` deben pertenecer a la variante lingüística correspondiente y ser válidos dentro del contexto en el que identifican el recurso.

El idioma semántico principal del documento debe corresponder al idioma activo del sistema.

Cuando una variante de contenido utiliza otro idioma mediante las reglas de respaldo, su región debe corresponder semánticamente al idioma real de esa variante sin cambiar el idioma principal del documento.

Los cambios lingüísticos internos definidos editorialmente deben conservarse durante el procesamiento y la representación del contenido.

Toda imagen de contenido debe incluir su fuente y su alternativa textual.

La alternativa textual debe permanecer vacía si su función corresponda a decorativa, sin omitirse ni utilizar un valor nulo.

La validación debe conservar el valor definido por `sitio-api` para cada representación sin exigir al frontend reconstruirlo a partir de otros datos.

La presentación debe conservar todo el contenido y toda la funcionalidad durante el redimensionamiento del texto, la ampliación y el reflujo.

La escala tipográfica debe responder al tamaño base configurado por el usuario.

Los componentes que contienen texto deben aumentar su espacio o reorganizarse cuando el contenido ampliado o el espaciado configurado por el usuario lo requieren.

No debe existir recorte, truncamiento, ocultación ni superposición provocados por estos cambios.

La página completa no debe adquirir desplazamiento horizontal durante el reflujo del contenido normal.

El desplazamiento horizontal propio debe limitarse a los componentes cuya estructura bidimensional necesita conservarse para mantener su uso, comprensión o significado.

Las cadenas textuales extensas deben ajustarse al espacio disponible cuando su división no altera el significado.

La aplicación debe conservar todo el contenido y toda la funcionalidad en las distintas orientaciones del dispositivo.

El cambio de orientación debe reutilizar las reglas responsive correspondientes al espacio disponible resultante.

Los controles interactivos independientes deben mantener un área de interacción suficiente y coherente con el tamaño general definido para los controles del sitio.

La superficie interactiva debe corresponder al control completo y no solamente a su contenido visual interior.

Los enlaces integrados en texto deben conservar su presentación textual.

La aplicación debe mantener disponibles simultáneamente los mecanismos de entrada compatibles con el dispositivo.

El uso de ratón, tacto, lápiz o teclado no debe provocar las mismas acciones.

Ninguna función necesaria debe depender exclusivamente de pasar el puntero sobre un elemento.

Los estados de puntero deben funcionar como retroalimentación visual adicional y no como condición necesaria para acceder a contenido o funcionalidad.

Las funciones propias de la aplicación no deben depender de gestos complejos, recorridos específicos ni movimientos físicos del dispositivo.

El arrastre no debe constituir el único mecanismo para realizar una operación.

Las acciones mediante puntero deben ejecutarse al completar la activación normal y deben permitir cancelar una interacción iniciada antes de completarla.

Cuando un control dispone de texto visible, su nombre accesible debe conservar ese texto.

Los gestos normales del navegador para desplazamiento, ampliación y demás funciones propias del agente de usuario no deben ser bloqueados por la aplicación.

Los bloques visuales de `Sobre mí` deben respetar los contratos correspondientes a su discriminador:

```text
type = icon
=> elemento de icono

type = image
=> src, alt y href obligatorios
```

Los elementos de Certificaciones deben respetar:

```text
type = certificate
=> contrato de certificado

type = certification
=> contrato Certification
```

Los artículos deben garantizar:

```text
update_date >= publication_date
```

La validación debe permitir detectar inconsistencias entre:

```text
Metadatos lingüísticos
Contenido disponible
Idioma original
Idiomas soportados por el contenido
Idioma semántico del documento
Idioma semántico del contenido
Cambios lingüísticos internos
Escala tipográfica
Redimensionamiento del texto
Reflujo
Adaptación de contenedores textuales
Espaciado del texto
Orientación
Tamaño de objetivos interactivos
Superficie interactiva de los controles
Interacción por ratón
Interacción táctil
Interacción mediante lápiz
Conservación simultánea de mecanismos de entrada
Dependencia del paso del puntero
Gestos de puntero
Arrastre
Cancelación de acciones de puntero
Nombres accesibles de controles con texto visible
Actuación mediante movimiento
Slug localizado
Elementos de interfaz
Selección de destacados
Orden de destacados
Actualizaciones
Fecha de actividad
Tipos de certificaciones
Fechas de artículos
Datos de proyectos
Imágenes de contenido
Alternativas textuales
Medios de contacto
Datos del formulario
```

## Pruebas

Las pruebas automatizadas verifican la lógica del frontend, los servicios, los componentes y la integración entre las partes de la aplicación.

`Vitest` constituye la herramienta principal para pruebas unitarias.

Las herramientas de pruebas de Angular proporcionan el entorno necesario para verificar componentes y servicios relacionados con el framework.

Las pruebas unitarias utilizan medición de cobertura y exigen una cobertura completa de instrucciones, ramas, funciones y líneas.

Los umbrales de cobertura forman parte de la configuración centralizada de las pruebas y deben impedir su aprobación cuando alguno de ellos no se alcanza.

La medición debe incluir el código de la aplicación sujeto a pruebas. La incorporación de componentes, servicios y demás funcionalidades requiere mantener la cobertura sobre el código correspondiente.

`Playwright` valida mediante navegador los flujos completos que requieran interacción con la aplicación.

Las pruebas de navegador se ejecutan mediante diferentes motores de navegación y verifican el comportamiento de la aplicación en los entornos configurados.

La prueba de navegador no se considera equivalente a la ejecución de un navegador concreto distinto cuando solamente comparten un mismo motor.

El entorno de desarrollo y las pruebas de navegador utilizan el servidor proporcionado por Angular sin depender de una construcción de producción previamente generada.

La suite automatizada solamente se considera aprobada cuando todas las pruebas ejecutadas terminan correctamente.

Conceptualmente:

```text
Pruebas automatizadas aprobadas en su totalidad
=> validación aprobada

Una o más pruebas automatizadas fallidas
=> validación fallida
=> no promover
```

Las pruebas deben cubrir especialmente:

```text
Resolución del idioma
Validación mediante los idiomas de interfaz
Persistencia de la preferencia
Selección manual
Idioma semántico principal del documento
Actualización del idioma semántico después de una selección manual
Conservación del idioma semántico durante la navegación interna
Contenido en el mismo idioma del sistema
Contenido presentado mediante idioma de respaldo
Declaración independiente del idioma de cada unidad de contenido
Colecciones con unidades presentadas en idiomas diferentes
Conservación del idioma del sistema en los textos de interfaz
Cambios lingüísticos internos dentro del contenido
Conservación de cambios lingüísticos durante el procesamiento de artículos
Navegación localizada
Slug localizado
Cambio de tema
Conservación del contenido durante el cambio de tema
Conservación del orden y la estructura durante el cambio de tema
Comunicación con sitio-api
Carga de Inicio
Estados de carga mediante skeleton
Estados vacíos
Errores de carga
Unidades completas e incompletas
Contenido no encontrado
Carga y error de cabecera
Carga y error de subelementos de navegación
Contenido destacado
Actualizaciones
Selección del idioma del contenido
Variante disponible
content = null
Respaldo mediante idioma por defecto
Respaldo mediante idioma original
Conservación del idioma activo del sistema
Aviso cuando el contenido utiliza otro idioma
Representación de Sobre mí
Discriminación entre icono e imagen
Alternativas textuales de imágenes de contenido
Conservación de la alternativa textual recibida
Alternativas vacías en representaciones resumidas
Alternativas informativas en representaciones de detalle
Alternativas de imágenes incluidas en artículos
Representación de Contactos mediante iconos
Mapeo de iconos de Tabler
Representación de tarjetas
Distribución adaptable de tarjetas
Composición de escritorio amplio
Composición de escritorio intermedio
Composición de pantallas estrechas
Reorganización de Actualizaciones
Cabecera responsive
Navegación lateral
Navegación en pantallas estrechas
Apertura y cierre del menú
Apertura y cierre de grupos de navegación
Restablecimiento del grupo después de navegar
Persistencia de los controles globales durante el desplazamiento
Adaptación de tipografía y espaciado
Escala tipográfica relativa
Respeto al tamaño base configurado por el usuario
Redimensionamiento del texto
Crecimiento de contenedores con contenido textual
Adaptación de controles con texto
Zoom del navegador sin restricciones
Reflujo de la interfaz
Conservación de contenido durante el reflujo
Conservación de funcionalidad durante el reflujo
Prevención del desplazamiento horizontal de la página
Desplazamiento horizontal interno limitado a contenido bidimensional necesario
Adaptación de cadenas textuales extensas
Espaciado personalizado entre líneas
Espaciado personalizado entre párrafos
Espaciado personalizado entre letras
Espaciado personalizado entre palabras
Conservación de contenido con espaciado cambiado
Conservación de funcionalidad con espaciado cambiado
Funcionamiento en orientación vertical
Funcionamiento en orientación horizontal
Cambio de orientación
Tamaño suficiente de objetivos interactivos independientes
Superficie interactiva correspondiente al control completo
Tamaño de objetivos de subelementos de navegación
Enlaces integrados dentro de texto
Interacción mediante ratón
Interacción mediante tacto
Interacción mediante lápiz
Conservación de la interacción mediante teclado junto con otros mecanismos
Conservación simultánea de mecanismos de entrada disponibles
Funcionamiento completo sin depender de pasar el puntero
Estados visuales de puntero como información adicional
Activación explícita de grupos de navegación
Ausencia de gestos complejos como requisito funcional
Ausencia de gestos multipunto como requisito funcional
Ausencia de recorridos específicos del puntero como requisito funcional
Ausencia de arrastre como requisito funcional
Alternativa mediante activación sencilla cuando exista una interacción de arrastre
Ejecución de acciones al completar la activación
Cancelación de una acción de puntero antes de completarla
Conservación del texto visible dentro del nombre accesible
Ausencia de actuación mediante movimiento como requisito funcional
Conservación de los gestos normales del navegador
Reorganización de componentes internos
Redimensionamiento proporcional de recursos visuales
Desplazamiento interno de contenidos anchos cuando sea necesario
Adaptación del formulario
Adaptación de Sobre mí
Listado de proyectos
Detalle de proyectos
Adaptación del detalle de proyectos
Representación de lenguajes y porcentajes
Listado de artículos
Fechas de publicación y actualización
Representación del contenido Markdown
Adaptación del contenido de artículos
Listado de certificados y certificaciones
Discriminación entre certificado y certificación
Adaptación del detalle de certificados y certificaciones
Representación de certificaciones sin expiración
Representación de credenciales no disponibles
Carga de medios de contacto
Envío del formulario de contacto
Envío en curso
Confirmación de envío
Validación del formulario
Conservación de valores tras validación o error
Protección honeypot sin estado visible propio
Tratamiento del límite de envíos
Fallo de envío
```

También debe verificarse que una variante ausente conserve `original` y `supported`, permitiendo que el frontend determine correctamente la siguiente solicitud.

