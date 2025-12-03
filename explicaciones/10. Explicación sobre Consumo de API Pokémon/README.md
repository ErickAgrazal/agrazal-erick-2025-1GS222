# Consumo de API Pokémon (Estilo Brutalista)

Este ejemplo demuestra cómo consumir una API externa (PokeAPI) utilizando `fetch` y `async/await`, manteniendo el patrón de arquitectura modular (IIFE) y aplicando un diseño visual estilo "Brutalismo".

## Implementación Técnica

### JavaScript (Patrón Modular)

Se mantiene estrictamente la estructura obligatoria:

1.  **`htmlElements`**: Referencias al formulario, input y contenedor de resultados.
2.  **`templates`**:
    *   `card`: Genera el HTML de la tarjeta del Pokémon (imagen, nombre, tipos, estadísticas).
    *   `error`: Plantilla para mensajes de error con estilo brutalista.
    *   `loading`: Indicador de carga simple.
3.  **`utils`**:
    *   `fetchPokemon(query)`: Función asíncrona que realiza la petición a `https://pokeapi.co/api/v2/pokemon/{query}`. Maneja errores de red y respuestas 404.
    *   `render(html)`: Inyecta el HTML generado en el contenedor.
4.  **`handlers`**:
    *   `onFormSubmit`: Orquesta el flujo: previene el envío por defecto, muestra el estado de carga, llama a la API y renderiza el resultado o el error.
5.  **`init`**: Asigna el listener al evento `submit` del formulario.

### CSS (Brutalismo)

El diseño sigue los principios del Brutalismo Web:
*   **Alto Contraste**: Bordes negros gruesos (`4px solid #000`) sobre fondos claros.
*   **Sombras Duras**: Sin difuminado (`box-shadow: 8px 8px 0px #000`), creando un efecto de profundidad "crudo".
*   **Tipografía**: Uso de fuentes monoespaciadas (`Courier New`) para un look técnico y despojado.
*   **Colores**: Paleta limitada con acentos fuertes (Rojo, Cyan) para destacar elementos interactivos.
*   **Layout**: Bloques definidos, márgenes amplios y elementos grandes.

## Cómo hacer llamados remotos con `fetch`

La API `fetch` proporciona una interfaz JavaScript para acceder y manipular partes del canal HTTP, tales como peticiones y respuestas.

### Estructura Básica

En este ejemplo utilizamos `async/await` para manejar las promesas de una manera más legible (parecido a código síncrono).

```javascript
// 1. Definimos la función como 'async'
async function obtenerDatos() {
    try {
        // 2. Hacemos la petición con 'await'
        // fetch devuelve una "Promesa" que se resuelve en la respuesta
        const response = await fetch('https://api.ejemplo.com/datos');

        // 3. Verificamos si la respuesta fue exitosa (status 200-299)
        if (!response.ok) {
            throw new Error('Error en la petición');
        }

        // 4. Convertimos el cuerpo de la respuesta a JSON
        // Esto también es una operación asíncrona
        const data = await response.json();

        return data;

    } catch (error) {
        // 5. Manejamos cualquier error de red o de la API
        console.error('Hubo un problema:', error);
    }
}
```

### Puntos Clave en el Código

En nuestra función `utils.fetchPokemon`:

1.  **`await fetch(...)`**: Pausa la ejecución hasta que el servidor responde.
2.  **`response.ok`**: Es crucial verificar esto. `fetch` no lanza error si la API devuelve un 404 (No encontrado), por lo que debemos verificarlo manualmente.
3.  **`await response.json()`**: Lee el stream de datos y lo parsea como objeto JavaScript.
4.  **`try/catch`**: Captura tanto errores de red (sin internet) como los errores que lanzamos manualmente si `response.ok` es falso.

## Uso

1.  Escribe el nombre de un Pokémon (ej: "pikachu", "mewtwo") o su número de ID en el campo de texto.
2.  Presiona "BUSCAR" o Enter.
3.  Observa la tarjeta con los datos o el mensaje de error si no se encuentra.
