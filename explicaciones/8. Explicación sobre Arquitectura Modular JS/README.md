# Arquitectura Modular en JavaScript

Este es el ejemplo más avanzado, que refactoriza la funcionalidad de la lista dinámica utilizando patrones de diseño profesionales y almacenamiento local.

> **⚠️ IMPORTANTE**: Este patrón de diseño basado en módulos (IIFE) es el estándar **obligatorio** que deben utilizar para el desarrollo del **último laboratorio** y el **proyecto semestral**.

## Estructura del Patrón Modular (IIFE)

El código debe estar encapsulado en una **Expresión de Función Ejecutada Inmediatamente (IIFE)** que retorne un objeto con el método `init`. El nombre del módulo principal debe ser `App`.

Dentro del módulo, es **obligatorio** mantener la siguiente estructura de objetos para organizar el código:

1.  **`htmlElements`**:
    *   Aquí se deben almacenar todas las referencias a los elementos del DOM (caché de selectores).
    *   Evita hacer `document.querySelector` dispersos por todo el código.

2.  **`templates`**:
    *   Contiene funciones que retornan cadenas de texto con código HTML (Template Strings).
    *   Separa la "vista" de la lógica. Reciben datos como argumentos y devuelven HTML formateado.

3.  **`utils`**:
    *   Funciones auxiliares y de utilidad que no son manejadores de eventos directos.
    *   Ejemplos: guardar/leer de `localStorage`, validaciones, formateo de datos, renderizado genérico.

4.  **`handlers`**:
    *   Funciones específicas que se ejecutan como respuesta a eventos (clicks, submits, changes).
    *   Deben llamar a funciones de `utils` o usar `templates` y `htmlElements` para realizar su trabajo.

5.  **`init`**:
    *   Método público que inicializa la aplicación.
    *   Aquí se asignan los *event listeners* iniciales y se ejecuta cualquier lógica de arranque (como cargar datos guardados).

## Plantilla Base (Boilerplate)

Pueden copiar y pegar esta estructura para iniciar sus proyectos:

```javascript
(() => {
    const App = (() => {
        // 1. Referencias al DOM
        const htmlElements = {
            form: document.querySelector('form'),
            input: document.querySelector('#miInput'),
            list: document.querySelector('#miLista'),
        };

        // 2. Plantillas HTML (Vistas)
        const templates = {
            item: (data) => `<li>${data}</li>`,
        };

        // 3. Funciones de Utilidad
        const utils = {
            render(data) {
                // Lógica para renderizar
            }
        };

        // 4. Manejadores de Eventos
        const handlers = {
            onFormSubmit(e) {
                e.preventDefault();
                // Lógica del evento
            }
        };

        // 5. Inicialización (API Pública)
        return {
            init() {
                // Asignar eventos iniciales
                if(htmlElements.form) {
                    htmlElements.form.addEventListener('submit', handlers.onFormSubmit);
                }
                // Lógica de arranque
                console.log('App iniciada');
            }
        };
    })();

    // Ejecutar la aplicación
    App.init();
})();
```

## Implementación del Ejemplo Actual

### HTML
- Estructura semántica para la aplicación.

### CSS
- **Diseño Avanzado**: Implementa "Glassmorphism" (efecto de vidrio esmerilado) usando fondos translúcidos y desenfoque (`backdrop-filter`).
- **Variables CSS**: Uso de `:root` para definir colores y valores reutilizables.
- **Diseño Responsivo**: Uso de `clamp()` para tipografía y espaciado adaptable.

### JavaScript
- **Patrón de Módulo (IIFE)**: Todo el código está encapsulado para evitar contaminar el alcance global.
- **Persistencia de Datos**: Uso de `localStorage` para guardar la lista de elementos, permitiendo que los datos persistan incluso después de recargar la página.
- **Inicialización**: Al cargar, verifica si hay datos guardados y reconstruye la lista automáticamente.

