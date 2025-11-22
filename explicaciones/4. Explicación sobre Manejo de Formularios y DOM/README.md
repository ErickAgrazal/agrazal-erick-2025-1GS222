# Manejo de Formularios y Manipulación del DOM (Acumulativo)

Este ejemplo extiende el manejo de formularios para permitir la acumulación de respuestas en el DOM.

## Implementación

### HTML
- Similar al ejemplo anterior, pero utiliza un `div` con id `response` para contener múltiples elementos.

### CSS
- Mantiene el tema oscuro y estilos de formulario consistentes.

### JavaScript
- **Inyección de HTML**: A diferencia del ejemplo anterior que usaba `textContent`, este utiliza `innerHTML +=` para agregar nuevo contenido HTML.
- **Acumulación**: Cada envío del formulario agrega un nuevo párrafo `<p>` al contenedor de respuestas, creando una lista histórica de los nombres ingresados en lugar de sobrescribir el anterior.
