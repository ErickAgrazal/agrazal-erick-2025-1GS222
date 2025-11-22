# Edición con LocalStorage y Navegación

Esta explicación es una refactorización del ejemplo anterior (Arquitectura Modular) para agregar la funcionalidad de **edición** en una página separada.

## Conceptos Clave

### 1. Cambio de Estrategia de Almacenamiento
En el ejemplo anterior, guardábamos el HTML completo en `localStorage`. Para permitir la edición, hemos cambiado a guardar **datos puros (JSON)**.
- **Antes**: `localStorage.setItem('response', '<div>...</div>')`
- **Ahora**: `localStorage.setItem('items', '["Juan", "Pedro", "Maria"]')`

Esto permite manipular los datos (agregar, eliminar, editar) fácilmente antes de generar el HTML.

### 2. Comunicación entre Páginas
Para editar un elemento en una página distinta (`edit.html`), necesitamos saber *qué* elemento editar.
- Al hacer clic en "Editar" en `index.html`, guardamos el índice del elemento en `localStorage` (`editIndex`).
- Al cargar `edit.html`, leemos ese índice y buscamos el dato correspondiente en la lista de items.

### 3. Flujo de Edición
1.  **Index**: El usuario hace clic en "Editar". Se guarda el índice y se redirige a `edit.html`.
2.  **Edit**: Se carga el valor actual en el input.
3.  **Guardar**: Al enviar el formulario, se actualiza el array de items en la posición específica, se guarda en `localStorage` y se redirige de vuelta a `index.html`.

## Estructura de Archivos

- `index.html`: Lista principal con opciones de Agregar, Eliminar y Editar.
- `edit.html`: Formulario para modificar un elemento existente.

## Implementación Técnica

Se mantiene el patrón modular (IIFE) con `App`, `htmlElements`, `templates`, `utils` y `handlers` en ambos archivos, asegurando consistencia y buenas prácticas.
