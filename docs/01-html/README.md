# HTML - Lenguaje de Marcado de Hipertexto

## Introducción

HTML es el lenguaje que usamos para estructurar el contenido de las páginas web. Piensen en HTML como el esqueleto de una página: define qué elementos existen y cómo están organizados, pero no cómo se ven (eso es trabajo de CSS) ni cómo se comportan (eso lo hace JavaScript).

## Conceptos Básicos

### ¿Qué es HTML?

HTML significa HyperText Markup Language. Es un lenguaje de marcado, no de programación. Esto significa que no tiene lógica o condicionales, simplemente describe la estructura y el contenido.

### Anatomía de un Elemento HTML

Un elemento HTML típico tiene tres partes:

```html
<p>Este es un párrafo</p>
```

1. **Etiqueta de apertura**: `<p>`
2. **Contenido**: Este es un párrafo
3. **Etiqueta de cierre**: `</p>`

Algunos elementos no tienen contenido y se cierran solos:

```html
<img src="foto.jpg" alt="Descripción">
<br>
<hr>
```

### Atributos

Los atributos proporcionan información adicional sobre los elementos:

```html
<a href="https://www.utp.ac.pa" target="_blank">Universidad Tecnológica</a>
<img src="logo.png" alt="Logo UTP" width="200">
<div id="contenedor" class="principal">Contenido</div>
```

## Estructura Básica de un Documento HTML

Todo documento HTML debe tener esta estructura mínima:

```html
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Mi Primera Página</title>
</head>
<body>
    <!-- Aquí va el contenido visible -->
</body>
</html>
```

Veamos qué hace cada parte:

- `<!DOCTYPE html>`: Le dice al navegador que use HTML5
- `<html>`: Elemento raíz que contiene todo
- `<head>`: Metadatos y configuración (no se ve en la página)
- `<body>`: Todo el contenido visible de la página

## Elementos de Texto

### Encabezados

HTML tiene seis niveles de encabezados, del más importante al menos importante:

```html
<h1>Título Principal</h1>
<h2>Subtítulo</h2>
<h3>Sección</h3>
<h4>Subsección</h4>
<h5>Apartado</h5>
<h6>Subapartado</h6>
```

**Importante**: Usen los encabezados por su importancia semántica, no por su tamaño. El tamaño lo controlamos con CSS.

### Párrafos y Saltos de Línea

```html
<p>Este es un párrafo. Puede contener varias oraciones.</p>
<p>Este es otro párrafo. Los párrafos se separan automáticamente.</p>

<p>Si necesitan un salto de línea<br>
dentro del mismo párrafo, usen br.</p>
```

### Formato de Texto

```html
<strong>Texto importante</strong>
<em>Texto enfatizado</em>
<mark>Texto resaltado</mark>
<small>Texto pequeño</small>
<del>Texto eliminado</del>
<ins>Texto insertado</ins>
<sub>subíndice</sub>
<sup>superíndice</sup>
```

## Listas

### Lista Desordenada

```html
<ul>
    <li>Primer elemento</li>
    <li>Segundo elemento</li>
    <li>Tercer elemento</li>
</ul>
```

### Lista Ordenada

```html
<ol>
    <li>Paso uno</li>
    <li>Paso dos</li>
    <li>Paso tres</li>
</ol>
```

### Lista de Descripción

```html
<dl>
    <dt>HTML</dt>
    <dd>Lenguaje de marcado para crear páginas web</dd>
    
    <dt>CSS</dt>
    <dd>Lenguaje para dar estilo a las páginas web</dd>
</dl>
```

## Enlaces y Navegación

Los enlaces son fundamentales en la web. Se crean con la etiqueta `<a>`:

```html
<!-- Enlace externo -->
<a href="https://www.google.com">Ir a Google</a>

<!-- Enlace interno -->
<a href="contacto.html">Contacto</a>

<!-- Enlace a sección de la misma página -->
<a href="#seccion-importante">Ir a sección</a>

<!-- Enlace de correo -->
<a href="mailto:correo@ejemplo.com">Enviar correo</a>

<!-- Enlace de teléfono -->
<a href="tel:+5071234567">Llamar</a>
```

## Imágenes y Multimedia

### Imágenes

```html
<img src="imagen.jpg" alt="Descripción de la imagen" width="500" height="300">
```

El atributo `alt` es crucial para accesibilidad. Describe la imagen para personas que usan lectores de pantalla o cuando la imagen no carga.

### Video

```html
<video width="320" height="240" controls>
    <source src="video.mp4" type="video/mp4">
    <source src="video.webm" type="video/webm">
    Tu navegador no soporta el elemento video.
</video>
```

### Audio

```html
<audio controls>
    <source src="audio.mp3" type="audio/mpeg">
    <source src="audio.ogg" type="audio/ogg">
    Tu navegador no soporta el elemento audio.
</audio>
```

## Tablas

Las tablas son para datos tabulares, no para diseño:

```html
<table>
    <thead>
        <tr>
            <th>Nombre</th>
            <th>Edad</th>
            <th>Ciudad</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>Juan</td>
            <td>22</td>
            <td>Panamá</td>
        </tr>
        <tr>
            <td>María</td>
            <td>25</td>
            <td>David</td>
        </tr>
    </tbody>
</table>
```

## Formularios

Los formularios son la forma principal de recoger información del usuario:

```html
<form action="/procesar" method="POST">
    <!-- Campo de texto -->
    <label for="nombre">Nombre:</label>
    <input type="text" id="nombre" name="nombre" required>
    
    <!-- Email -->
    <label for="email">Correo:</label>
    <input type="email" id="email" name="email" required>
    
    <!-- Contraseña -->
    <label for="password">Contraseña:</label>
    <input type="password" id="password" name="password">
    
    <!-- Número -->
    <label for="edad">Edad:</label>
    <input type="number" id="edad" name="edad" min="1" max="120">
    
    <!-- Radio buttons -->
    <p>Género:</p>
    <input type="radio" id="masculino" name="genero" value="M">
    <label for="masculino">Masculino</label>
    
    <input type="radio" id="femenino" name="genero" value="F">
    <label for="femenino">Femenino</label>
    
    <!-- Checkbox -->
    <input type="checkbox" id="terminos" name="terminos">
    <label for="terminos">Acepto los términos</label>
    
    <!-- Select -->
    <label for="pais">País:</label>
    <select id="pais" name="pais">
        <option value="">Seleccione...</option>
        <option value="PA">Panamá</option>
        <option value="CR">Costa Rica</option>
        <option value="CO">Colombia</option>
    </select>
    
    <!-- Textarea -->
    <label for="comentarios">Comentarios:</label>
    <textarea id="comentarios" name="comentarios" rows="4" cols="50"></textarea>
    
    <!-- Botones -->
    <button type="submit">Enviar</button>
    <button type="reset">Limpiar</button>
</form>
```

### Tipos de Input Modernos

HTML5 introdujo nuevos tipos de input muy útiles:

```html
<input type="date" name="fecha">
<input type="time" name="hora">
<input type="datetime-local" name="fecha-hora">
<input type="color" name="color">
<input type="range" name="volumen" min="0" max="100">
<input type="file" name="archivo">
<input type="search" name="busqueda">
<input type="tel" name="telefono">
<input type="url" name="sitio-web">
```

## Elementos Semánticos

HTML5 introdujo elementos semánticos que describen mejor el propósito del contenido:

```html
<header>
    <nav>
        <ul>
            <li><a href="#inicio">Inicio</a></li>
            <li><a href="#servicios">Servicios</a></li>
            <li><a href="#contacto">Contacto</a></li>
        </ul>
    </nav>
</header>

<main>
    <section>
        <h2>Servicios</h2>
        <article>
            <h3>Desarrollo Web</h3>
            <p>Creamos sitios web modernos...</p>
        </article>
    </section>
    
    <aside>
        <h3>Enlaces relacionados</h3>
        <ul>
            <li><a href="#">Recurso 1</a></li>
            <li><a href="#">Recurso 2</a></li>
        </ul>
    </aside>
</main>

<footer>
    <p>&copy; 2025 Universidad Tecnológica de Panamá</p>
</footer>
```

Estos elementos hacen que el código sea más legible y ayudan con el SEO y la accesibilidad.

## Elementos de Agrupación

### div y span

`<div>` y `<span>` son contenedores genéricos:

- `<div>`: Elemento de bloque (ocupa todo el ancho disponible)
- `<span>`: Elemento en línea (solo ocupa el espacio necesario)

```html
<div class="contenedor">
    <p>Este es un párrafo dentro de un div.</p>
    <p>Otro párrafo con <span class="resaltado">texto resaltado</span> dentro.</p>
</div>
```

### figure y figcaption

Para imágenes con descripciones:

```html
<figure>
    <img src="grafico.png" alt="Gráfico de ventas">
    <figcaption>Ventas del primer trimestre 2025</figcaption>
</figure>
```

## Buenas Prácticas

1. **Siempre usen DOCTYPE**: `<!DOCTYPE html>`

2. **Especifiquen el idioma**: `<html lang="es">`

3. **Incluyan meta viewport para móviles**:
   ```html
   <meta name="viewport" content="width=device-width, initial-scale=1.0">
   ```

4. **Usen elementos semánticos** cuando sea posible

5. **Siempre incluyan alt en imágenes**

6. **Validen su HTML**: Pueden usar el validador de W3C

7. **Mantengan la estructura limpia y bien indentada**

8. **No usen HTML para estilos** (eso es trabajo de CSS)

9. **Asocien labels con inputs** usando el atributo `for`

10. **Piensen en accesibilidad** desde el principio

## Ejercicio Práctico

Creen una página personal que incluya:

1. Una estructura HTML5 completa
2. Un encabezado con navegación
3. Una sección "Sobre mí" con párrafos y una foto
4. Una lista de habilidades
5. Una tabla con proyectos realizados
6. Un formulario de contacto
7. Un pie de página

Este ejercicio les ayudará a practicar todos los conceptos básicos de HTML.

## Recursos Adicionales

- [MDN Web Docs - HTML](https://developer.mozilla.org/es/docs/Web/HTML)
- [W3Schools HTML Tutorial](https://www.w3schools.com/html/)
- [HTML Validator](https://validator.w3.org/)

Recuerden: HTML es la base de todo en el desarrollo web. Domínenlo bien antes de pasar a CSS y JavaScript. La práctica constante es la clave para aprenderlo.