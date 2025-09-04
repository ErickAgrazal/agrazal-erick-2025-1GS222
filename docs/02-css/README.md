# CSS - Hojas de Estilo en Cascada

## Introducción

Si HTML es el esqueleto de una página web, CSS es la ropa, el maquillaje y todo lo que la hace verse bien. CSS nos permite controlar colores, tamaños, espaciados, animaciones y prácticamente cualquier aspecto visual de nuestra página.

## Formas de Incluir CSS

Hay tres formas de agregar CSS a nuestro HTML:

### 1. CSS en Línea (Inline)
```html
<p style="color: blue; font-size: 20px;">Este texto es azul</p>
```
No es recomendable. Dificulta el mantenimiento y no se puede reutilizar.

### 2. CSS Interno (En el head)
```html
<head>
    <style>
        p {
            color: blue;
            font-size: 20px;
        }
    </style>
</head>
```
Útil para páginas únicas, pero no ideal para sitios grandes.

### 3. CSS Externo (Archivo separado)
```html
<head>
    <link rel="stylesheet" href="estilos.css">
</head>
```
La mejor opción. Permite reutilizar estilos y mantener el código organizado.

## Sintaxis Básica

Una regla CSS tiene tres partes:

```css
selector {
    propiedad: valor;
    otra-propiedad: otro-valor;
}
```

Por ejemplo:
```css
p {
    color: blue;
    font-size: 16px;
    margin: 10px;
}
```

## Selectores

Los selectores determinan a qué elementos HTML se aplican los estilos.

### Selectores Básicos

```css
/* Selector de elemento */
p {
    color: blue;
}

/* Selector de clase */
.destacado {
    background-color: yellow;
}

/* Selector de ID */
#cabecera {
    height: 100px;
}

/* Selector universal */
* {
    margin: 0;
    padding: 0;
}
```

### Selectores Combinados

```css
/* Descendiente (espacio) */
div p {
    color: red;  /* Todos los p dentro de div */
}

/* Hijo directo (>) */
div > p {
    color: blue;  /* Solo p que son hijos directos de div */
}

/* Hermano adyacente (+) */
h2 + p {
    margin-top: 0;  /* p inmediatamente después de h2 */
}

/* Hermanos generales (~) */
h2 ~ p {
    color: gray;  /* Todos los p hermanos después de h2 */
}
```

### Selectores de Atributo

```css
/* Tiene el atributo */
[type] {
    border: 1px solid black;
}

/* Atributo con valor específico */
[type="text"] {
    background-color: white;
}

/* Atributo que empieza con */
[href^="https"] {
    color: green;
}

/* Atributo que termina con */
[src$=".jpg"] {
    border: 2px solid red;
}

/* Atributo que contiene */
[class*="col-"] {
    float: left;
}
```

### Pseudo-clases

Las pseudo-clases seleccionan elementos en estados específicos:

```css
/* Estados de enlaces */
a:link { color: blue; }
a:visited { color: purple; }
a:hover { color: red; }
a:active { color: orange; }

/* Posición en lista */
li:first-child { font-weight: bold; }
li:last-child { margin-bottom: 0; }
li:nth-child(2n) { background: #f0f0f0; }  /* Pares */
li:nth-child(odd) { background: white; }   /* Impares */

/* Estados de formulario */
input:focus { border-color: blue; }
input:disabled { opacity: 0.5; }
input:checked { background: green; }
```

### Pseudo-elementos

Los pseudo-elementos permiten estilizar partes específicas de un elemento:

```css
/* Primera letra y línea */
p::first-letter {
    font-size: 2em;
    font-weight: bold;
}

p::first-line {
    color: blue;
}

/* Contenido antes y después */
.nota::before {
    content: "Nota: ";
    font-weight: bold;
}

.precio::after {
    content: " USD";
    font-size: 0.8em;
}

/* Selección de texto */
::selection {
    background: yellow;
    color: black;
}
```

## El Modelo de Caja (Box Model)

Todos los elementos HTML son cajas rectangulares. Entender el box model es fundamental:

```css
.caja {
    /* Contenido */
    width: 300px;
    height: 200px;
    
    /* Padding (relleno interno) */
    padding: 20px;
    /* También: padding-top, padding-right, padding-bottom, padding-left */
    
    /* Border (borde) */
    border: 2px solid black;
    
    /* Margin (margen externo) */
    margin: 10px;
    
    /* Box-sizing */
    box-sizing: border-box;  /* Incluye padding y border en width/height */
}
```

### Propiedades Shorthand

```css
/* Padding/Margin: arriba derecha abajo izquierda */
padding: 10px 20px 10px 20px;

/* Padding/Margin: vertical horizontal */
padding: 10px 20px;

/* Border: ancho estilo color */
border: 1px solid #333;
```

## Colores y Fondos

### Colores

```css
.colores {
    /* Nombres de colores */
    color: red;
    
    /* Hexadecimal */
    background-color: #ff0000;
    background-color: #f00;  /* Forma corta */
    
    /* RGB */
    color: rgb(255, 0, 0);
    
    /* RGBA (con transparencia) */
    background-color: rgba(255, 0, 0, 0.5);
    
    /* HSL */
    color: hsl(0, 100%, 50%);
    
    /* HSLA */
    background-color: hsla(0, 100%, 50%, 0.5);
}
```

### Fondos

```css
.fondo {
    /* Color de fondo */
    background-color: #f0f0f0;
    
    /* Imagen de fondo */
    background-image: url('imagen.jpg');
    
    /* Repetición */
    background-repeat: no-repeat;  /* repeat, repeat-x, repeat-y */
    
    /* Posición */
    background-position: center center;
    
    /* Tamaño */
    background-size: cover;  /* contain, 100px 100px, 50% */
    
    /* Fijación */
    background-attachment: fixed;  /* scroll */
    
    /* Shorthand */
    background: #f0f0f0 url('imagen.jpg') no-repeat center/cover;
}
```

### Gradientes

```css
.gradiente {
    /* Gradiente lineal */
    background: linear-gradient(to right, red, blue);
    background: linear-gradient(45deg, #fff, #000);
    
    /* Gradiente radial */
    background: radial-gradient(circle, red, yellow, green);
    
    /* Múltiples colores */
    background: linear-gradient(to right, 
        red 0%, 
        orange 20%, 
        yellow 40%, 
        green 60%, 
        blue 80%, 
        purple 100%);
}
```

## Tipografía

### Propiedades de Fuente

```css
.texto {
    /* Familia de fuente */
    font-family: Arial, Helvetica, sans-serif;
    
    /* Tamaño */
    font-size: 16px;  /* px, em, rem, %, vw */
    
    /* Peso */
    font-weight: bold;  /* normal, bold, 100-900 */
    
    /* Estilo */
    font-style: italic;  /* normal, italic, oblique */
    
    /* Variante */
    font-variant: small-caps;
    
    /* Shorthand */
    font: italic bold 16px/1.5 Arial, sans-serif;
}
```

### Propiedades de Texto

```css
.parrafo {
    /* Color */
    color: #333;
    
    /* Alineación */
    text-align: center;  /* left, right, justify */
    
    /* Decoración */
    text-decoration: underline;  /* none, overline, line-through */
    
    /* Transformación */
    text-transform: uppercase;  /* lowercase, capitalize */
    
    /* Espaciado entre letras */
    letter-spacing: 2px;
    
    /* Espaciado entre palabras */
    word-spacing: 5px;
    
    /* Altura de línea */
    line-height: 1.5;
    
    /* Sangría */
    text-indent: 20px;
    
    /* Sombra */
    text-shadow: 2px 2px 4px rgba(0,0,0,0.5);
}
```

### Fuentes Web

```css
/* Google Fonts */
@import url('https://fonts.googleapis.com/css2?family=Roboto:wght@300;400;700&display=swap');

/* Fuentes personalizadas */
@font-face {
    font-family: 'MiFuente';
    src: url('mifuente.woff2') format('woff2'),
         url('mifuente.woff') format('woff');
}

body {
    font-family: 'Roboto', sans-serif;
}
```

## Layout y Posicionamiento

### Display

```css
.elemento {
    /* Valores comunes */
    display: block;        /* Ocupa todo el ancho */
    display: inline;       /* Solo el espacio necesario */
    display: inline-block; /* Híbrido */
    display: none;         /* Oculta el elemento */
    display: flex;         /* Contenedor flexible */
    display: grid;         /* Contenedor de cuadrícula */
}
```

### Position

```css
/* Static (por defecto) */
.estatico {
    position: static;
}

/* Relative */
.relativo {
    position: relative;
    top: 10px;
    left: 20px;
}

/* Absolute */
.absoluto {
    position: absolute;
    top: 0;
    right: 0;
}

/* Fixed */
.fijo {
    position: fixed;
    bottom: 20px;
    right: 20px;
}

/* Sticky */
.pegajoso {
    position: sticky;
    top: 0;
}
```

### Float y Clear

```css
.imagen {
    float: left;  /* right */
    margin-right: 10px;
}

.limpiar {
    clear: both;  /* left, right */
}
```

## Flexbox

Flexbox es genial para layouts unidimensionales:

```css
/* Contenedor */
.flex-container {
    display: flex;
    
    /* Dirección */
    flex-direction: row;  /* column, row-reverse, column-reverse */
    
    /* Ajuste de línea */
    flex-wrap: wrap;  /* nowrap, wrap-reverse */
    
    /* Alineación principal */
    justify-content: center;  /* flex-start, flex-end, space-between, space-around, space-evenly */
    
    /* Alineación cruzada */
    align-items: center;  /* flex-start, flex-end, stretch, baseline */
    
    /* Alineación de líneas */
    align-content: center;
    
    /* Espacio entre elementos */
    gap: 10px;
}

/* Elementos hijos */
.flex-item {
    /* Crecimiento */
    flex-grow: 1;
    
    /* Encogimiento */
    flex-shrink: 1;
    
    /* Tamaño base */
    flex-basis: 200px;
    
    /* Shorthand */
    flex: 1 1 200px;
    
    /* Alineación individual */
    align-self: flex-start;
    
    /* Orden */
    order: 2;
}
```

## Grid

Grid es perfecto para layouts bidimensionales:

```css
/* Contenedor */
.grid-container {
    display: grid;
    
    /* Columnas */
    grid-template-columns: 1fr 2fr 1fr;
    grid-template-columns: repeat(3, 1fr);
    grid-template-columns: 200px auto 200px;
    
    /* Filas */
    grid-template-rows: 100px auto 50px;
    
    /* Espaciado */
    gap: 10px;
    /* O específicamente: */
    row-gap: 10px;
    column-gap: 20px;
    
    /* Áreas nombradas */
    grid-template-areas:
        "header header header"
        "sidebar main main"
        "footer footer footer";
}

/* Elementos hijos */
.grid-item {
    /* Posición específica */
    grid-column: 1 / 3;  /* De columna 1 a 3 */
    grid-row: 1 / 2;
    
    /* O usando áreas */
    grid-area: header;
    
    /* Alineación individual */
    justify-self: center;
    align-self: center;
}
```

## Diseño Responsivo

### Media Queries

```css
/* Móvil primero */
.contenedor {
    width: 100%;
    padding: 10px;
}

/* Tablets */
@media (min-width: 768px) {
    .contenedor {
        width: 750px;
        margin: 0 auto;
    }
}

/* Desktop */
@media (min-width: 1024px) {
    .contenedor {
        width: 960px;
    }
}

/* Desktop grande */
@media (min-width: 1440px) {
    .contenedor {
        width: 1200px;
    }
}

/* Orientación */
@media (orientation: landscape) {
    /* Estilos para pantalla horizontal */
}

/* Print */
@media print {
    /* Estilos para impresión */
}
```

### Unidades Responsivas

```css
.responsivo {
    /* Viewport width/height */
    width: 50vw;   /* 50% del ancho del viewport */
    height: 100vh; /* 100% de la altura del viewport */
    
    /* Relative to font-size */
    font-size: 2rem;  /* 2 veces el tamaño de fuente raíz */
    padding: 1em;     /* 1 vez el tamaño de fuente del elemento */
    
    /* Porcentaje */
    width: 100%;
    
    /* Calc */
    width: calc(100% - 20px);
    
    /* Min/Max */
    width: min(500px, 100%);
    width: max(300px, 50%);
    width: clamp(300px, 50%, 500px);
}
```

## Transiciones y Animaciones

### Transiciones

```css
.boton {
    background-color: blue;
    transition: background-color 0.3s ease;
    
    /* O múltiples propiedades */
    transition: all 0.3s ease-in-out;
    
    /* Propiedades individuales */
    transition-property: background-color, transform;
    transition-duration: 0.3s;
    transition-timing-function: ease-in-out;
    transition-delay: 0.1s;
}

.boton:hover {
    background-color: red;
    transform: scale(1.1);
}
```

### Animaciones

```css
/* Definir la animación */
@keyframes girar {
    0% {
        transform: rotate(0deg);
    }
    100% {
        transform: rotate(360deg);
    }
}

/* Aplicar la animación */
.spinner {
    animation: girar 2s linear infinite;
    
    /* Propiedades individuales */
    animation-name: girar;
    animation-duration: 2s;
    animation-timing-function: linear;
    animation-iteration-count: infinite;
    animation-direction: normal;  /* reverse, alternate */
    animation-fill-mode: forwards;  /* backwards, both */
}

/* Animación compleja */
@keyframes rebote {
    0%, 100% {
        transform: translateY(0);
    }
    50% {
        transform: translateY(-20px);
    }
}
```

## Transformaciones

```css
.transformado {
    /* Trasladar */
    transform: translateX(50px);
    transform: translateY(-20px);
    transform: translate(50px, -20px);
    
    /* Rotar */
    transform: rotate(45deg);
    
    /* Escalar */
    transform: scale(1.5);
    transform: scaleX(2);
    
    /* Sesgar */
    transform: skew(10deg, 5deg);
    
    /* Múltiples transformaciones */
    transform: rotate(45deg) scale(1.2) translateX(50px);
    
    /* Origen de transformación */
    transform-origin: top left;
}
```

## Variables CSS (Custom Properties)

```css
:root {
    /* Definir variables */
    --color-primario: #007bff;
    --color-secundario: #6c757d;
    --espaciado: 16px;
    --fuente-principal: 'Helvetica', sans-serif;
}

/* Usar variables */
.elemento {
    color: var(--color-primario);
    padding: var(--espaciado);
    font-family: var(--fuente-principal);
    
    /* Con valor por defecto */
    margin: var(--margen, 10px);
}

/* Cambiar variables en diferentes contextos */
.tema-oscuro {
    --color-primario: #4dabff;
    --color-secundario: #adb5bd;
}
```

## Especificidad y Cascada

La especificidad determina qué estilos se aplican cuando hay conflictos:

1. **Inline styles**: 1000 puntos
2. **IDs**: 100 puntos
3. **Clases, pseudo-clases, atributos**: 10 puntos
4. **Elementos**: 1 punto

```css
/* Especificidad: 0-0-1 */
p { color: red; }

/* Especificidad: 0-1-0 */
.texto { color: blue; }

/* Especificidad: 1-0-0 */
#principal { color: green; }

/* Especificidad: 0-1-1 */
p.texto { color: yellow; }

/* Especificidad: 1-1-0 */
#principal.texto { color: orange; }

/* !important rompe todo (evítenlo) */
p { color: purple !important; }
```

## Buenas Prácticas

1. **Organicen su CSS**: Agrupen estilos relacionados
2. **Usen nombres descriptivos**: `.boton-principal` mejor que `.btn1`
3. **Eviten IDs para estilos**: Son muy específicos
4. **Mantengan la especificidad baja**: Facilita el mantenimiento
5. **Usen variables CSS**: Para colores y valores repetidos
6. **Mobile First**: Diseñen primero para móvil
7. **Eviten !important**: Casi siempre hay una mejor solución
8. **Comenten el código complejo**: Ayuda a otros (y a ustedes mismos)
9. **Validen su CSS**: Usen herramientas como el validador de W3C
10. **Consideren usar metodologías**: BEM, SMACSS, etc.

## Ejercicio Práctico

Creen una página de portafolio que incluya:

1. Un header fijo con navegación
2. Una sección hero con gradiente de fondo
3. Cards de proyectos usando Grid
4. Formulario de contacto estilizado
5. Footer con links usando Flexbox
6. Transiciones en hover
7. Diseño completamente responsivo
8. Variables CSS para colores y espaciados

## Recursos Adicionales

- [MDN CSS](https://developer.mozilla.org/es/docs/Web/CSS)
- [CSS Tricks](https://css-tricks.com/)
- [Can I Use](https://caniuse.com/) - Compatibilidad de navegadores
- [Flexbox Froggy](https://flexboxfroggy.com/) - Juego para aprender Flexbox
- [Grid Garden](https://cssgridgarden.com/) - Juego para aprender Grid

CSS puede parecer simple al principio, pero tiene mucha profundidad. La clave es practicar constantemente y experimentar con diferentes propiedades. No se frustren si algo no sale como esperan; debugging CSS es parte del proceso de aprendizaje.