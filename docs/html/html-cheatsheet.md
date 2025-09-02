# 🚀 HTML Cheat Sheet - Referencia Rápida

## 🏗️ Estructura Básica

```html
<!DOCTYPE html>                     <!-- Declara HTML5 -->
<html lang="es">                    <!-- Elemento raíz, idioma español -->
<head>                              <!-- Metadatos (no visible) -->
    <meta charset="UTF-8">          <!-- Codificación de caracteres -->
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Título de la página</title>
</head>
<body>                              <!-- Contenido visible -->
    <!-- Tu contenido aquí -->
</body>
</html>
```

## 📝 Etiquetas de Texto

### Encabezados
```html
<h1>Encabezado 1 (más importante)</h1>
<h2>Encabezado 2</h2>
<h3>Encabezado 3</h3>
<h4>Encabezado 4</h4>
<h5>Encabezado 5</h5>
<h6>Encabezado 6 (menos importante)</h6>
```

### Párrafos y Formato
```html
<p>Párrafo normal</p>
<br>                                <!-- Salto de línea -->
<hr>                                <!-- Línea horizontal -->
<strong>Texto importante</strong>   <!-- Negrita semántica -->
<b>Texto en negrita</b>            <!-- Negrita visual -->
<em>Texto enfatizado</em>          <!-- Cursiva semántica -->
<i>Texto en cursiva</i>            <!-- Cursiva visual -->
<mark>Texto resaltado</mark>       <!-- Resaltado amarillo -->
<small>Texto pequeño</small>
<del>Texto eliminado</del>         <!-- Tachado -->
<ins>Texto insertado</ins>         <!-- Subrayado -->
<sub>Subíndice</sub>
<sup>Superíndice</sup>
<code>código en línea</code>
<pre>Texto preformateado</pre>
<blockquote>Cita larga</blockquote>
<q>Cita corta</q>
<cite>Fuente de cita</cite>
<abbr title="Significado">ABR</abbr>  <!-- Abreviatura -->
```

## 🔗 Enlaces

```html
<!-- Enlaces básicos -->
<a href="https://ejemplo.com">Enlace externo</a>
<a href="pagina.html">Enlace interno</a>
<a href="#seccion">Enlace a sección</a>
<a href="/">Inicio</a>

<!-- Enlaces especiales -->
<a href="mailto:email@ejemplo.com">Enviar email</a>
<a href="tel:+507-6000-0000">Llamar</a>
<a href="archivo.pdf" download>Descargar</a>

<!-- Atributos de enlaces -->
<a href="url" target="_blank">Nueva pestaña</a>
<a href="url" target="_self">Misma pestaña</a>
<a href="url" title="Descripción">Con tooltip</a>
<a href="url" rel="nofollow">Sin seguimiento SEO</a>
```

## 🖼️ Imágenes

```html
<!-- Imagen básica -->
<img src="imagen.jpg" alt="Descripción">

<!-- Con dimensiones -->
<img src="foto.png" width="300" height="200">

<!-- Lazy loading (carga diferida) -->
<img src="pesada.jpg" loading="lazy">

<!-- Picture responsivo -->
<picture>
    <source media="(min-width: 800px)" srcset="grande.jpg">
    <source media="(min-width: 400px)" srcset="mediana.jpg">
    <img src="pequena.jpg" alt="Imagen adaptable">
</picture>

<!-- Figure con caption -->
<figure>
    <img src="grafico.png" alt="Gráfico">
    <figcaption>Descripción del gráfico</figcaption>
</figure>
```

## 📋 Listas

```html
<!-- Lista desordenada -->
<ul>
    <li>Elemento 1</li>
    <li>Elemento 2</li>
</ul>

<!-- Lista ordenada -->
<ol>
    <li>Primero</li>
    <li>Segundo</li>
</ol>

<!-- Lista ordenada con tipo -->
<ol type="A">    <!-- A, a, I, i, 1 -->
    <li>Opción A</li>
    <li>Opción B</li>
</ol>

<!-- Lista de definiciones -->
<dl>
    <dt>Término</dt>
    <dd>Definición</dd>
</dl>

<!-- Listas anidadas -->
<ul>
    <li>Item
        <ul>
            <li>Sub-item</li>
        </ul>
    </li>
</ul>
```

## 📊 Tablas

```html
<table>
    <caption>Título de tabla</caption>
    <thead>
        <tr>
            <th>Encabezado 1</th>
            <th>Encabezado 2</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>Dato 1</td>
            <td>Dato 2</td>
        </tr>
    </tbody>
    <tfoot>
        <tr>
            <td>Total</td>
            <td>100</td>
        </tr>
    </tfoot>
</table>

<!-- Celdas combinadas -->
<td colspan="2">Ocupa 2 columnas</td>
<td rowspan="2">Ocupa 2 filas</td>
```

## 📝 Formularios

### Estructura Básica
```html
<form action="/procesar" method="POST">
    <!-- Campos del formulario -->
    <button type="submit">Enviar</button>
</form>
```

### Input Types
```html
<!-- Texto -->
<input type="text" name="nombre" placeholder="Tu nombre">
<input type="email" name="email" required>
<input type="password" name="clave" minlength="8">
<input type="tel" name="telefono" pattern="[0-9]{4}-[0-9]{4}">
<input type="url" name="web">
<input type="search" name="buscar">

<!-- Números y rangos -->
<input type="number" min="0" max="100" step="5">
<input type="range" min="0" max="10" value="5">

<!-- Fecha y hora -->
<input type="date" name="fecha">
<input type="time" name="hora">
<input type="datetime-local" name="fecha-hora">
<input type="month" name="mes">
<input type="week" name="semana">

<!-- Selección -->
<input type="checkbox" name="acepto" value="si">
<input type="radio" name="genero" value="m">
<input type="radio" name="genero" value="f">

<!-- Otros -->
<input type="color" name="color">
<input type="file" name="archivo" accept=".pdf,.doc">
<input type="hidden" name="id" value="123">

<!-- Botones -->
<input type="submit" value="Enviar">
<input type="reset" value="Limpiar">
<input type="button" value="Click" onclick="funcion()">
```

### Otros Elementos de Formulario
```html
<!-- Área de texto -->
<textarea name="mensaje" rows="5" cols="30"></textarea>

<!-- Lista desplegable -->
<select name="pais">
    <option value="">Seleccione</option>
    <option value="PA">Panamá</option>
    <option value="CR" selected>Costa Rica</option>
</select>

<!-- Select múltiple -->
<select name="idiomas" multiple size="3">
    <option>Español</option>
    <option>Inglés</option>
    <option>Francés</option>
</select>

<!-- Label (etiqueta) -->
<label for="email">Email:</label>
<input type="email" id="email" name="email">

<!-- Fieldset (agrupar campos) -->
<fieldset>
    <legend>Información Personal</legend>
    <!-- campos aquí -->
</fieldset>

<!-- Datalist (sugerencias) -->
<input list="navegadores">
<datalist id="navegadores">
    <option value="Chrome">
    <option value="Firefox">
    <option value="Safari">
</datalist>

<!-- Button -->
<button type="submit">Enviar</button>
<button type="reset">Limpiar</button>
<button type="button">Normal</button>
```

### Atributos Comunes de Formulario
```html
required                <!-- Campo obligatorio -->
readonly               <!-- Solo lectura -->
disabled               <!-- Deshabilitado -->
autofocus             <!-- Foco automático -->
autocomplete="off"     <!-- Sin autocompletado -->
pattern="[A-Z]{3}"    <!-- Patrón regex -->
placeholder="texto"    <!-- Texto de ayuda -->
value="valor"         <!-- Valor por defecto -->
maxlength="10"        <!-- Longitud máxima -->
minlength="5"         <!-- Longitud mínima -->
min="0"               <!-- Valor mínimo -->
max="100"             <!-- Valor máximo -->
step="5"              <!-- Incremento -->
multiple              <!-- Selección múltiple -->
```

## 🎬 Multimedia

### Video
```html
<video controls width="640" height="360">
    <source src="video.mp4" type="video/mp4">
    <source src="video.webm" type="video/webm">
    Tu navegador no soporta video.
</video>

<!-- Atributos de video -->
controls              <!-- Controles de reproducción -->
autoplay             <!-- Reproducción automática -->
muted                <!-- Silenciado -->
loop                 <!-- Repetir -->
poster="imagen.jpg"  <!-- Imagen de vista previa -->
preload="auto"       <!-- Precargar: none|metadata|auto -->
```

### Audio
```html
<audio controls>
    <source src="audio.mp3" type="audio/mpeg">
    <source src="audio.ogg" type="audio/ogg">
    Tu navegador no soporta audio.
</audio>
```

### Iframe
```html
<!-- YouTube -->
<iframe src="https://www.youtube.com/embed/VIDEO_ID" 
        width="560" height="315" 
        frameborder="0" allowfullscreen>
</iframe>

<!-- Página web -->
<iframe src="https://ejemplo.com" 
        width="100%" height="400">
</iframe>
```

## 🏛️ HTML5 Semántico

```html
<header>     <!-- Cabecera de página o sección -->
<nav>        <!-- Navegación -->
<main>       <!-- Contenido principal -->
<section>    <!-- Sección temática -->
<article>    <!-- Contenido independiente -->
<aside>      <!-- Contenido tangencial -->
<footer>     <!-- Pie de página o sección -->

<figure>     <!-- Figura o ilustración -->
<figcaption> <!-- Descripción de figura -->
<time>       <!-- Fecha/hora -->
<mark>       <!-- Texto resaltado -->
<details>    <!-- Detalles expandibles -->
<summary>    <!-- Resumen de details -->
<dialog>     <!-- Cuadro de diálogo -->
<progress>   <!-- Barra de progreso -->
<meter>      <!-- Medidor -->
<output>     <!-- Resultado de cálculo -->
```

## 🏷️ Meta Tags Importantes

```html
<!-- Esenciales -->
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<meta name="description" content="Descripción de la página">
<meta name="keywords" content="palabra1, palabra2">
<meta name="author" content="Nombre del autor">

<!-- Open Graph (Redes Sociales) -->
<meta property="og:title" content="Título">
<meta property="og:description" content="Descripción">
<meta property="og:image" content="imagen.jpg">
<meta property="og:url" content="https://ejemplo.com">

<!-- Twitter Card -->
<meta name="twitter:card" content="summary">
<meta name="twitter:title" content="Título">
<meta name="twitter:description" content="Descripción">
<meta name="twitter:image" content="imagen.jpg">

<!-- Otros -->
<meta name="robots" content="index, follow">
<meta http-equiv="refresh" content="30">
<link rel="canonical" href="https://ejemplo.com">
<link rel="icon" type="image/png" href="favicon.png">
```

## 🎨 Elementos de División

```html
<div>        <!-- División genérica (bloque) -->
<span>       <!-- División genérica (línea) -->
<header>     <!-- Cabecera -->
<nav>        <!-- Navegación -->
<main>       <!-- Contenido principal -->
<section>    <!-- Sección -->
<article>    <!-- Artículo -->
<aside>      <!-- Lateral -->
<footer>     <!-- Pie -->
```

## 🔤 Caracteres Especiales (Entidades HTML)

```html
&lt;         <!-- < (menor que) -->
&gt;         <!-- > (mayor que) -->
&amp;        <!-- & (ampersand) -->
&quot;       <!-- " (comillas) -->
&apos;       <!-- ' (apóstrofe) -->
&nbsp;       <!-- Espacio sin ruptura -->
&copy;       <!-- © (copyright) -->
&reg;        <!-- ® (registrado) -->
&trade;      <!-- ™ (trademark) -->
&euro;       <!-- € (euro) -->
&pound;      <!-- £ (libra) -->
&yen;        <!-- ¥ (yen) -->
&cent;       <!-- ¢ (centavo) -->
&deg;        <!-- ° (grados) -->
&frac12;     <!-- ½ (un medio) -->
&frac14;     <!-- ¼ (un cuarto) -->
&times;      <!-- × (multiplicación) -->
&divide;     <!-- ÷ (división) -->
&plusmn;     <!-- ± (más/menos) -->
&mdash;      <!-- — (guión largo) -->
&ndash;      <!-- – (guión medio) -->
&hellip;     <!-- … (puntos suspensivos) -->
&larr;       <!-- ← (flecha izquierda) -->
&rarr;       <!-- → (flecha derecha) -->
&uarr;       <!-- ↑ (flecha arriba) -->
&darr;       <!-- ↓ (flecha abajo) -->
```

## 📏 Atributos Globales

```html
id="unico"           <!-- Identificador único -->
class="clase1 clase2" <!-- Clases CSS -->
style="color: red;"  <!-- Estilos inline -->
title="Tooltip"      <!-- Texto emergente -->
lang="es"           <!-- Idioma -->
dir="ltr"           <!-- Dirección texto: ltr|rtl -->
hidden              <!-- Oculto -->
tabindex="1"        <!-- Orden de tabulación -->
contenteditable     <!-- Editable -->
spellcheck          <!-- Corrector ortográfico -->
draggable           <!-- Arrastrable -->
data-*="valor"      <!-- Atributos personalizados -->
```

## 🚀 Plantilla Rápida de Inicio

```html
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="description" content="Descripción de tu sitio">
    <title>Mi Sitio Web</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <header>
        <nav>
            <a href="/">Inicio</a>
            <a href="/sobre">Sobre</a>
            <a href="/contacto">Contacto</a>
        </nav>
    </header>
    
    <main>
        <h1>Bienvenido</h1>
        <p>Contenido principal aquí.</p>
    </main>
    
    <footer>
        <p>&copy; 2024 Mi Sitio. Todos los derechos reservados.</p>
    </footer>
    
    <script src="script.js"></script>
</body>
</html>
```

## 💡 Tips Rápidos

1. **Siempre usa** `alt` en imágenes para accesibilidad
2. **Siempre usa** `label` con inputs de formulario
3. **Valida tu HTML** en validator.w3.org
4. **Usa HTML semántico** en lugar de divs genéricos
5. **Declara el idioma** con `lang` en `<html>`
6. **Incluye viewport** para diseño responsive
7. **Minifica HTML** para producción
8. **Usa HTTPS** para enlaces externos
9. **Optimiza imágenes** antes de subirlas
10. **Comenta tu código** para facilitar mantenimiento

## 🔍 Validación y Testing

```bash
# Validar HTML local
# https://validator.w3.org/#validate_by_upload

# Validar HTML en línea
# https://validator.w3.org/#validate_by_uri

# Verificar accesibilidad
# https://wave.webaim.org/

# Verificar SEO
# Lighthouse en Chrome DevTools
```

---

*📖 Para más detalles, consulta la [guía completa](./README.md) o visita [MDN Web Docs](https://developer.mozilla.org/es/docs/Web/HTML)*