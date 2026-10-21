# 13. Cabecera

La cabecera constituye una única unidad visual.

Mientras se obtienen sus datos, conserva su espacio estructural y utiliza una representación skeleton adaptada a su composición.

La cabecera solamente se presenta como contenido cuando los elementos necesarios para constituirla se encuentran disponibles.

Si la unidad no debe cargarse completamente, la región de cabecera presenta un estado de error.

El mensaje utiliza una representación localizada equivalente a:

```text
No fue posible cargar la información de la cabecera.

Actualice la página para volver a intentarlo.
```

Una falla de la cabecera no elimina la navegación ni invalida otras regiones que puedan continuar funcionando.

