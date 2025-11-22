# Introducción a JavaScript

Este ejemplo demuestra los conceptos básicos de interacción con el DOM y manejo de eventos en JavaScript.

## Implementación

### HTML
- Estructura básica con un título `<h1>`, un contenedor `<span>` para mensajes y un botón `<button>`.

### CSS
- Estilos simples para el botón (borde redondeado, cursor pointer).
- Efecto `hover` en el botón.
- Clase utilitaria `.red` para cambiar el color del texto.

### JavaScript
- **Interpolación de Strings**: Uso de template literals (`` ` ``) para insertar variables en cadenas de texto.
- **Selección de Elementos**: Uso de `document.querySelector` para obtener referencias a elementos del DOM.
- **Manipulación de Texto**: Uso de `.textContent` para modificar el contenido del `<span>`.
- **Eventos**: `addEventListener` para escuchar el evento `click` en el botón.
- **Clases CSS**: Uso de `classList.toggle("red")` para alternar la clase `.red` en el elemento `span`, cambiando su color dinámicamente.
