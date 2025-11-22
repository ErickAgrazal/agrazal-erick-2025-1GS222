# Formulario Acumulativo JS

Variante del formulario que demuestra la persistencia visual temporal (acumulación) en el DOM.

## Implementación

### HTML
- Estructura idéntica al formulario simple.

### CSS
- Mismos estilos oscuros y de botones.

### JavaScript
- **Acumulación de Elementos**: Utiliza `innerHTML +=` para concatenar nuevos párrafos `<p>` al contenedor de respuesta.
- **Diferencia Clave**: A diferencia de `textContent` que reemplaza, esta técnica permite ver el historial de entradas realizadas durante la sesión (hasta que se recargue la página).
