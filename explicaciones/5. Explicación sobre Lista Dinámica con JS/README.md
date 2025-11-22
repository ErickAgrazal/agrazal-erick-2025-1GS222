# Lista Dinámica con JavaScript (Agregar y Eliminar)

Este ejemplo implementa una lista dinámica completa donde se pueden agregar elementos y eliminarlos individualmente, manteniendo un contador actualizado.

## Implementación

### HTML
- Formulario de entrada.
- Un contador (`div#counter`) para mostrar la cantidad de elementos.
- Un contenedor (`div#response`) para la lista de elementos.

### CSS
- Estilos oscuros consistentes.

### JavaScript
- **Generación Dinámica de Elementos**: Al enviar el formulario, se agrega un párrafo que incluye el nombre y un botón "Eliminar".
- **Delegación de Eventos (Simulada)**: Después de agregar un elemento, se seleccionan todos los botones de eliminar y se les asigna un evento `click`.
- **Eliminación de Elementos**: Al hacer clic en "Eliminar", se busca el elemento padre (`closest('p')`) y se elimina del DOM con `.remove()`.
- **Contador Dinámico**: Se actualiza el texto del contador (`#counter`) cada vez que se agrega o elimina un elemento, basándose en `response.children.length`.
