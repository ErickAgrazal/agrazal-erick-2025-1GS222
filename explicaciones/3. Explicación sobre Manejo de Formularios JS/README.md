# Manejo de Formularios con JavaScript

Este ejemplo ilustra cómo capturar y procesar datos enviados a través de un formulario HTML.

## Implementación

### HTML
- Formulario simple con un campo de entrada (`input`) y un botón de envío.
- Un elemento `<span>` con id `response` para mostrar el resultado.

### CSS
- Tema oscuro (`background-color: black`, `color: white`).
- Centrado de elementos y estilos básicos de formulario.

### JavaScript
- **Evento Submit**: Escucha el evento `submit` del formulario en lugar del click del botón, lo cual es la práctica estándar para formularios.
- **Prevención de Recarga**: Uso de `e.preventDefault()` para evitar que la página se recargue al enviar el formulario.
- **Captura de Valores**: Obtención del valor del input mediante `input.value`.
- **Respuesta Única**: Muestra un mensaje de saludo en el `span`, reemplazando cualquier contenido anterior (`textContent`).
