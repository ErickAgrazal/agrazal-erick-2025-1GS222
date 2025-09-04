# JavaScript - El Lenguaje de la Web

## Introducción

JavaScript es lo que hace que las páginas web cobren vida. Si HTML es la estructura y CSS es el estilo, JavaScript es el cerebro que permite interactividad, lógica y comunicación con servidores. A diferencia de HTML y CSS, JavaScript es un lenguaje de programación real, con variables, funciones, condicionales y todo lo necesario para crear aplicaciones complejas.

## Primeros Pasos

### Cómo Incluir JavaScript

Hay tres formas de agregar JavaScript a tu HTML:

```html
<!-- JavaScript inline (evitar) -->
<button onclick="alert('Hola!')">Clic aquí</button>

<!-- JavaScript interno -->
<script>
    console.log('Hola desde el script interno');
</script>

<!-- JavaScript externo (recomendado) -->
<script src="script.js"></script>
```

El script externo es la mejor práctica. Normalmente lo ponemos justo antes de cerrar `</body>` para que el HTML cargue primero.

### La Consola

La consola del navegador es tu mejor amiga. Presiona F12 y ve a la pestaña Console:

```javascript
console.log('Mensaje normal');
console.error('Mensaje de error');
console.warn('Advertencia');
console.table(['dato1', 'dato2', 'dato3']);
```

## Variables y Tipos de Datos

### Declaración de Variables

En JavaScript moderno usamos `let` y `const`:

```javascript
// const para valores que no cambian
const PI = 3.14159;
const nombre = "Juan";

// let para valores que pueden cambiar
let edad = 20;
let estaActivo = true;

// var es antiguo, evítenlo
var noUsenEsto = "en serio";
```

### Tipos de Datos

JavaScript tiene varios tipos de datos:

```javascript
// Números
let entero = 42;
let decimal = 3.14;
let negativo = -10;

// Strings (cadenas de texto)
let texto = "Hola mundo";
let texto2 = 'También con comillas simples';
let texto3 = `Template literal con ${entero}`;

// Booleanos
let verdadero = true;
let falso = false;

// Undefined y Null
let sinDefinir;  // undefined
let vacio = null;

// Arrays
let numeros = [1, 2, 3, 4, 5];
let mixto = ["texto", 42, true, null];

// Objetos
let persona = {
    nombre: "María",
    edad: 25,
    activo: true
};

// Funciones (también son un tipo de dato)
let saludar = function() {
    console.log("Hola!");
};
```

### Template Literals

Los template literals (con backticks) son muy útiles:

```javascript
let nombre = "Pedro";
let edad = 30;

// Concatenación antigua
let mensaje1 = "Hola, me llamo " + nombre + " y tengo " + edad + " años";

// Template literal (mucho mejor)
let mensaje2 = `Hola, me llamo ${nombre} y tengo ${edad} años`;

// Múltiples líneas
let html = `
    <div>
        <h1>${nombre}</h1>
        <p>Edad: ${edad}</p>
    </div>
`;
```

## Operadores

### Operadores Aritméticos

```javascript
let a = 10;
let b = 3;

console.log(a + b);  // 13 - Suma
console.log(a - b);  // 7  - Resta
console.log(a * b);  // 30 - Multiplicación
console.log(a / b);  // 3.333... - División
console.log(a % b);  // 1  - Módulo (resto)
console.log(a ** b); // 1000 - Potencia

// Incremento y decremento
a++;  // a = 11
b--;  // b = 2
```

### Operadores de Asignación

```javascript
let x = 10;

x += 5;  // x = x + 5  -> 15
x -= 3;  // x = x - 3  -> 12
x *= 2;  // x = x * 2  -> 24
x /= 4;  // x = x / 4  -> 6
x %= 4;  // x = x % 4  -> 2
```

### Operadores de Comparación

```javascript
let a = 5;
let b = "5";

// Igualdad débil (convierte tipos)
console.log(a == b);   // true

// Igualdad estricta (no convierte tipos)
console.log(a === b);  // false

// Desigualdad
console.log(a != b);   // false
console.log(a !== b);  // true

// Mayor/menor
console.log(a > 3);    // true
console.log(a < 10);   // true
console.log(a >= 5);   // true
console.log(a <= 5);   // true
```

### Operadores Lógicos

```javascript
let edad = 20;
let tieneID = true;

// AND (&&) - ambas deben ser true
if (edad >= 18 && tieneID) {
    console.log("Puede entrar");
}

// OR (||) - al menos una debe ser true
if (edad < 18 || !tieneID) {
    console.log("No puede entrar");
}

// NOT (!) - niega el valor
console.log(!true);   // false
console.log(!false);  // true
```

## Control de Flujo

### Condicionales

```javascript
// if simple
let edad = 20;

if (edad >= 18) {
    console.log("Es mayor de edad");
}

// if...else
if (edad >= 18) {
    console.log("Es mayor de edad");
} else {
    console.log("Es menor de edad");
}

// if...else if...else
let nota = 85;

if (nota >= 90) {
    console.log("A");
} else if (nota >= 80) {
    console.log("B");
} else if (nota >= 70) {
    console.log("C");
} else {
    console.log("F");
}

// Operador ternario
let mensaje = edad >= 18 ? "Mayor" : "Menor";
```

### Switch

```javascript
let dia = 3;
let nombreDia;

switch (dia) {
    case 1:
        nombreDia = "Lunes";
        break;
    case 2:
        nombreDia = "Martes";
        break;
    case 3:
        nombreDia = "Miércoles";
        break;
    case 4:
        nombreDia = "Jueves";
        break;
    case 5:
        nombreDia = "Viernes";
        break;
    case 6:
    case 7:
        nombreDia = "Fin de semana";
        break;
    default:
        nombreDia = "Día inválido";
}
```

## Bucles

### For

```javascript
// For clásico
for (let i = 0; i < 5; i++) {
    console.log(i);  // 0, 1, 2, 3, 4
}

// For...of (para arrays)
let frutas = ["manzana", "pera", "uva"];

for (let fruta of frutas) {
    console.log(fruta);
}

// For...in (para objetos)
let persona = {nombre: "Ana", edad: 25, ciudad: "Panamá"};

for (let propiedad in persona) {
    console.log(`${propiedad}: ${persona[propiedad]}`);
}
```

### While y Do...While

```javascript
// While
let contador = 0;

while (contador < 5) {
    console.log(contador);
    contador++;
}

// Do...while (ejecuta al menos una vez)
let numero = 0;

do {
    console.log(numero);
    numero++;
} while (numero < 5);
```

### Break y Continue

```javascript
// Break - sale del bucle
for (let i = 0; i < 10; i++) {
    if (i === 5) {
        break;
    }
    console.log(i);  // 0, 1, 2, 3, 4
}

// Continue - salta a la siguiente iteración
for (let i = 0; i < 5; i++) {
    if (i === 2) {
        continue;
    }
    console.log(i);  // 0, 1, 3, 4
}
```

## Funciones

### Declaración de Funciones

```javascript
// Función declarada
function saludar(nombre) {
    return `Hola, ${nombre}!`;
}

// Función expresada
const despedir = function(nombre) {
    return `Adiós, ${nombre}!`;
};

// Arrow function (función flecha)
const multiplicar = (a, b) => {
    return a * b;
};

// Arrow function simplificada
const dividir = (a, b) => a / b;

// Llamando funciones
console.log(saludar("Carlos"));
console.log(multiplicar(5, 3));
```

### Parámetros y Argumentos

```javascript
// Parámetros por defecto
function crearUsuario(nombre, edad = 18, activo = true) {
    return {
        nombre: nombre,
        edad: edad,
        activo: activo
    };
}

// Rest parameters
function sumarTodos(...numeros) {
    let total = 0;
    for (let num of numeros) {
        total += num;
    }
    return total;
}

console.log(sumarTodos(1, 2, 3, 4, 5));  // 15

// Desestructuración en parámetros
function mostrarPersona({nombre, edad}) {
    console.log(`${nombre} tiene ${edad} años`);
}

mostrarPersona({nombre: "Luis", edad: 30});
```

### Scope (Alcance)

```javascript
// Scope global
let global = "Soy global";

function miFuncion() {
    // Scope de función
    let local = "Soy local";
    
    if (true) {
        // Scope de bloque
        let bloque = "Soy de bloque";
        console.log(global);  // ✓ Accesible
        console.log(local);   // ✓ Accesible
        console.log(bloque);  // ✓ Accesible
    }
    
    console.log(global);  // ✓ Accesible
    console.log(local);   // ✓ Accesible
    // console.log(bloque);  // ✗ Error! No accesible
}

miFuncion();
// console.log(local);  // ✗ Error! No accesible
```

## Arrays

### Métodos Básicos

```javascript
let frutas = ["manzana", "pera", "uva"];

// Agregar elementos
frutas.push("naranja");      // Al final
frutas.unshift("fresa");     // Al inicio

// Eliminar elementos
let ultima = frutas.pop();   // Elimina y retorna el último
let primera = frutas.shift(); // Elimina y retorna el primero

// Buscar elementos
let indice = frutas.indexOf("pera");  // Retorna el índice o -1
let existe = frutas.includes("uva");  // Retorna true o false

// Otros métodos útiles
let longitud = frutas.length;
let copia = frutas.slice();  // Copia superficial
frutas.reverse();  // Invierte el array
frutas.sort();     // Ordena alfabéticamente
```

### Métodos de Array Avanzados

```javascript
let numeros = [1, 2, 3, 4, 5];

// map - transforma cada elemento
let dobles = numeros.map(n => n * 2);
console.log(dobles);  // [2, 4, 6, 8, 10]

// filter - filtra elementos
let pares = numeros.filter(n => n % 2 === 0);
console.log(pares);  // [2, 4]

// reduce - reduce a un solo valor
let suma = numeros.reduce((total, n) => total + n, 0);
console.log(suma);  // 15

// find - encuentra el primer elemento
let mayor3 = numeros.find(n => n > 3);
console.log(mayor3);  // 4

// some - verifica si alguno cumple
let hayPares = numeros.some(n => n % 2 === 0);
console.log(hayPares);  // true

// every - verifica si todos cumplen
let todosPositivos = numeros.every(n => n > 0);
console.log(todosPositivos);  // true

// forEach - ejecuta función para cada elemento
numeros.forEach(n => console.log(n * 2));
```

### Spread Operator

```javascript
let arr1 = [1, 2, 3];
let arr2 = [4, 5, 6];

// Combinar arrays
let combinado = [...arr1, ...arr2];  // [1, 2, 3, 4, 5, 6]

// Copiar array
let copia = [...arr1];

// Usar en funciones
let maximo = Math.max(...arr1);  // 3
```

## Objetos

### Creación y Acceso

```javascript
// Crear objeto
let persona = {
    nombre: "Ana",
    edad: 25,
    activo: true,
    hobbies: ["leer", "correr"],
    direccion: {
        calle: "Principal",
        numero: 123
    }
};

// Acceder a propiedades
console.log(persona.nombre);  // Notación de punto
console.log(persona["edad"]); // Notación de corchetes

// Agregar/modificar propiedades
persona.telefono = "123-4567";
persona.edad = 26;

// Eliminar propiedad
delete persona.activo;
```

### Métodos de Objeto

```javascript
let usuario = {
    nombre: "Carlos",
    edad: 30,
    // Método
    saludar: function() {
        return `Hola, soy ${this.nombre}`;
    },
    // Método con sintaxis corta
    despedir() {
        return "Adiós!";
    }
};

console.log(usuario.saludar());
```

### Desestructuración

```javascript
let persona = {
    nombre: "Laura",
    edad: 28,
    ciudad: "Panamá"
};

// Desestructuración básica
let {nombre, edad} = persona;

// Con alias
let {nombre: name, edad: age} = persona;

// Con valores por defecto
let {nombre, telefono = "Sin teléfono"} = persona;

// En arrays
let colores = ["rojo", "verde", "azul"];
let [primero, segundo] = colores;

// Ignorar elementos
let [primer, , tercer] = colores;
```

### Object Methods

```javascript
let coche = {
    marca: "Toyota",
    modelo: "Corolla",
    año: 2020
};

// Obtener keys
let keys = Object.keys(coche);  // ["marca", "modelo", "año"]

// Obtener valores
let valores = Object.values(coche);  // ["Toyota", "Corolla", 2020]

// Obtener entries
let entries = Object.entries(coche);  // [["marca", "Toyota"], ...]

// Congelar objeto (no se puede modificar)
Object.freeze(coche);

// Sellar objeto (no se pueden agregar/eliminar propiedades)
Object.seal(coche);
```

## El DOM (Document Object Model)

### Seleccionar Elementos

```javascript
// Por ID
let elemento = document.getElementById("miId");

// Por clase
let elementos = document.getElementsByClassName("miClase");

// Por etiqueta
let parrafos = document.getElementsByTagName("p");

// querySelector (retorna el primero)
let primero = document.querySelector(".clase");
let elemento2 = document.querySelector("#id");

// querySelectorAll (retorna todos)
let todos = document.querySelectorAll(".clase");
```

### Modificar Elementos

```javascript
let elemento = document.querySelector("#miElemento");

// Cambiar texto
elemento.textContent = "Nuevo texto";

// Cambiar HTML
elemento.innerHTML = "<strong>Texto en negrita</strong>";

// Cambiar atributos
elemento.setAttribute("class", "nueva-clase");
elemento.id = "nuevoId";

// Cambiar estilos
elemento.style.color = "red";
elemento.style.fontSize = "20px";
elemento.style.display = "none";

// Agregar/quitar clases
elemento.classList.add("activo");
elemento.classList.remove("inactivo");
elemento.classList.toggle("visible");
```

### Crear y Eliminar Elementos

```javascript
// Crear elemento
let nuevoDiv = document.createElement("div");
nuevoDiv.textContent = "Soy nuevo";
nuevoDiv.className = "caja";

// Agregar al DOM
document.body.appendChild(nuevoDiv);

// Insertar antes de otro elemento
let contenedor = document.querySelector("#contenedor");
let referencia = document.querySelector("#referencia");
contenedor.insertBefore(nuevoDiv, referencia);

// Eliminar elemento
let elemento = document.querySelector("#eliminar");
elemento.remove();

// O desde el padre
elemento.parentNode.removeChild(elemento);
```

## Eventos

### Agregar Event Listeners

```javascript
let boton = document.querySelector("#miBoton");

// Forma recomendada
boton.addEventListener("click", function() {
    console.log("Clic!");
});

// Con arrow function
boton.addEventListener("click", () => {
    console.log("Clic con arrow!");
});

// Función separada
function manejarClic(evento) {
    console.log("Clic desde función");
    console.log(evento.target);  // El elemento clickeado
}

boton.addEventListener("click", manejarClic);
```

### Tipos de Eventos Comunes

```javascript
// Mouse
elemento.addEventListener("click", fn);      // Clic
elemento.addEventListener("dblclick", fn);   // Doble clic
elemento.addEventListener("mouseenter", fn); // Mouse entra
elemento.addEventListener("mouseleave", fn); // Mouse sale
elemento.addEventListener("mousemove", fn);  // Mouse se mueve

// Teclado
document.addEventListener("keydown", fn);    // Tecla presionada
document.addEventListener("keyup", fn);      // Tecla soltada
document.addEventListener("keypress", fn);   // Tecla presionada (obsoleto)

// Formulario
form.addEventListener("submit", fn);         // Envío de formulario
input.addEventListener("change", fn);        // Cambio de valor
input.addEventListener("input", fn);         // Mientras escribe
input.addEventListener("focus", fn);         // Cuando recibe foco
input.addEventListener("blur", fn);          // Cuando pierde foco

// Documento
document.addEventListener("DOMContentLoaded", fn); // DOM listo
window.addEventListener("load", fn);         // Todo cargado
window.addEventListener("resize", fn);       // Ventana redimensionada
window.addEventListener("scroll", fn);       // Scroll
```

### Event Object

```javascript
boton.addEventListener("click", function(evento) {
    // Prevenir comportamiento por defecto
    evento.preventDefault();
    
    // Detener propagación
    evento.stopPropagation();
    
    // Información del evento
    console.log(evento.type);        // "click"
    console.log(evento.target);      // Elemento clickeado
    console.log(evento.currentTarget); // Elemento con el listener
    console.log(evento.clientX);     // Posición X del mouse
    console.log(evento.clientY);     // Posición Y del mouse
});
```

### Delegación de Eventos

```javascript
// En lugar de agregar listener a cada elemento
let lista = document.querySelector("#lista");

lista.addEventListener("click", function(e) {
    // Verificar si el clic fue en un li
    if (e.target.tagName === "LI") {
        console.log("Clickeaste: " + e.target.textContent);
    }
});
```

## Formularios

### Trabajando con Formularios

```javascript
let formulario = document.querySelector("#miFormulario");

formulario.addEventListener("submit", function(e) {
    e.preventDefault();  // Evitar envío tradicional
    
    // Obtener valores
    let nombre = document.querySelector("#nombre").value;
    let email = document.querySelector("#email").value;
    let edad = parseInt(document.querySelector("#edad").value);
    
    // Validación básica
    if (nombre.length < 3) {
        alert("Nombre muy corto");
        return;
    }
    
    if (!email.includes("@")) {
        alert("Email inválido");
        return;
    }
    
    if (edad < 18) {
        alert("Debes ser mayor de edad");
        return;
    }
    
    // Procesar datos
    console.log("Formulario válido!");
    console.log({nombre, email, edad});
});
```

### Validación en Tiempo Real

```javascript
let inputEmail = document.querySelector("#email");
let errorMsg = document.querySelector("#error-email");

inputEmail.addEventListener("input", function() {
    let valor = this.value;
    
    if (!valor.includes("@")) {
        this.classList.add("error");
        errorMsg.textContent = "Email debe contener @";
        errorMsg.style.display = "block";
    } else {
        this.classList.remove("error");
        errorMsg.style.display = "none";
    }
});
```

## JSON

JSON (JavaScript Object Notation) es el formato estándar para intercambiar datos:

```javascript
// Objeto JavaScript
let persona = {
    nombre: "Pedro",
    edad: 30,
    activo: true
};

// Convertir a JSON string
let json = JSON.stringify(persona);
console.log(json);  // '{"nombre":"Pedro","edad":30,"activo":true}'

// Convertir de JSON a objeto
let texto = '{"nombre":"Ana","edad":25}';
let objeto = JSON.parse(texto);
console.log(objeto.nombre);  // Ana
```

## LocalStorage y SessionStorage

Permiten guardar datos en el navegador:

```javascript
// LocalStorage (persiste incluso cerrando el navegador)
localStorage.setItem("nombre", "Carlos");
localStorage.setItem("config", JSON.stringify({tema: "oscuro"}));

let nombre = localStorage.getItem("nombre");
let config = JSON.parse(localStorage.getItem("config"));

localStorage.removeItem("nombre");
localStorage.clear();  // Elimina todo

// SessionStorage (se borra al cerrar la pestaña)
sessionStorage.setItem("temporal", "dato");
let temp = sessionStorage.getItem("temporal");
```

## Manejo de Errores

```javascript
try {
    // Código que puede fallar
    let resultado = funcionQuePodriaFallar();
    console.log(resultado);
} catch (error) {
    // Manejar el error
    console.error("Ocurrió un error:", error.message);
} finally {
    // Se ejecuta siempre
    console.log("Limpieza");
}

// Lanzar errores propios
function dividir(a, b) {
    if (b === 0) {
        throw new Error("No se puede dividir por cero");
    }
    return a / b;
}
```

## Asincronía

### setTimeout y setInterval

```javascript
// Ejecutar después de un tiempo
setTimeout(function() {
    console.log("Han pasado 2 segundos");
}, 2000);

// Ejecutar repetidamente
let contador = 0;
let intervalo = setInterval(function() {
    contador++;
    console.log("Contador:", contador);
    
    if (contador >= 5) {
        clearInterval(intervalo);  // Detener
    }
}, 1000);
```

### Promesas

```javascript
// Crear una promesa
function esperar(segundos) {
    return new Promise((resolve, reject) => {
        if (segundos < 0) {
            reject("El tiempo no puede ser negativo");
        }
        
        setTimeout(() => {
            resolve(`Esperé ${segundos} segundos`);
        }, segundos * 1000);
    });
}

// Usar la promesa
esperar(2)
    .then(resultado => {
        console.log(resultado);
        return esperar(1);
    })
    .then(resultado => {
        console.log(resultado);
    })
    .catch(error => {
        console.error(error);
    });
```

### Async/Await

```javascript
// Función asíncrona
async function procesarDatos() {
    try {
        console.log("Empezando...");
        
        // Esperar promesa
        let resultado1 = await esperar(2);
        console.log(resultado1);
        
        let resultado2 = await esperar(1);
        console.log(resultado2);
        
        console.log("Terminado!");
    } catch (error) {
        console.error("Error:", error);
    }
}

procesarDatos();
```

### Fetch API

```javascript
// GET request
async function obtenerDatos() {
    try {
        let respuesta = await fetch('https://jsonplaceholder.typicode.com/users');
        let datos = await respuesta.json();
        console.log(datos);
    } catch (error) {
        console.error("Error al obtener datos:", error);
    }
}

// POST request
async function enviarDatos() {
    try {
        let respuesta = await fetch('https://jsonplaceholder.typicode.com/posts', {
            method: 'POST',
            headers: {
                'Content-Type': 'application/json'
            },
            body: JSON.stringify({
                title: 'Mi post',
                body: 'Contenido del post',
                userId: 1
            })
        });
        
        let resultado = await respuesta.json();
        console.log("Post creado:", resultado);
    } catch (error) {
        console.error("Error al enviar:", error);
    }
}
```

## Clases

JavaScript moderno soporta clases (aunque internamente siguen siendo prototipos):

```javascript
class Persona {
    // Constructor
    constructor(nombre, edad) {
        this.nombre = nombre;
        this.edad = edad;
    }
    
    // Métodos
    saludar() {
        return `Hola, soy ${this.nombre}`;
    }
    
    cumplir() {
        this.edad++;
        console.log(`Ahora tengo ${this.edad} años`);
    }
    
    // Getter
    get info() {
        return `${this.nombre} (${this.edad} años)`;
    }
    
    // Setter
    set nuevoNombre(valor) {
        if (valor.length < 2) {
            throw new Error("Nombre muy corto");
        }
        this.nombre = valor;
    }
    
    // Método estático
    static especie() {
        return "Homo sapiens";
    }
}

// Usar la clase
let persona = new Persona("Luis", 25);
console.log(persona.saludar());
persona.cumplir();
console.log(persona.info);
console.log(Persona.especie());

// Herencia
class Estudiante extends Persona {
    constructor(nombre, edad, carrera) {
        super(nombre, edad);  // Llamar constructor padre
        this.carrera = carrera;
    }
    
    estudiar() {
        return `${this.nombre} está estudiando ${this.carrera}`;
    }
    
    // Sobrescribir método
    saludar() {
        return `Hola, soy ${this.nombre} y estudio ${this.carrera}`;
    }
}

let estudiante = new Estudiante("Ana", 20, "Ingeniería");
console.log(estudiante.estudiar());
console.log(estudiante.saludar());
```

## Módulos

Los módulos permiten organizar el código en archivos separados:

```javascript
// math.js - Exportar
export function sumar(a, b) {
    return a + b;
}

export function restar(a, b) {
    return a - b;
}

export const PI = 3.14159;

// Exportación por defecto
export default function multiplicar(a, b) {
    return a * b;
}

// main.js - Importar
import multiplicar, { sumar, restar, PI } from './math.js';

console.log(sumar(5, 3));
console.log(multiplicar(4, 2));
```

En HTML:
```html
<script type="module" src="main.js"></script>
```

## Buenas Prácticas

1. **Usen const y let**, nunca var
2. **Nombres descriptivos** para variables y funciones
3. **Funciones pequeñas** que hagan una sola cosa
4. **Eviten el código repetido** (DRY - Don't Repeat Yourself)
5. **Manejen errores** con try/catch
6. **Validen datos** especialmente de usuarios
7. **Comenten código complejo**, no el obvio
8. **Usen === en lugar de ==** para comparaciones
9. **Eviten variables globales** cuando sea posible
10. **Mantengan el código organizado** en módulos

## Proyecto Práctico: Lista de Tareas

Aquí un ejemplo completo que integra muchos conceptos:

```html
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <title>Lista de Tareas</title>
</head>
<body>
    <h1>Mi Lista de Tareas</h1>
    
    <form id="formulario-tarea">
        <input type="text" id="nueva-tarea" placeholder="Nueva tarea..." required>
        <button type="submit">Agregar</button>
    </form>
    
    <ul id="lista-tareas"></ul>
    <button id="limpiar-completadas">Limpiar Completadas</button>
    
    <script src="app.js"></script>
</body>
</html>
```

```javascript
// app.js
class ListaTareas {
    constructor() {
        this.tareas = this.cargarTareas();
        this.formulario = document.querySelector('#formulario-tarea');
        this.input = document.querySelector('#nueva-tarea');
        this.lista = document.querySelector('#lista-tareas');
        this.botonLimpiar = document.querySelector('#limpiar-completadas');
        
        this.inicializarEventos();
        this.renderizar();
    }
    
    inicializarEventos() {
        this.formulario.addEventListener('submit', (e) => {
            e.preventDefault();
            this.agregarTarea();
        });
        
        this.lista.addEventListener('click', (e) => {
            if (e.target.classList.contains('eliminar')) {
                this.eliminarTarea(e.target.dataset.id);
            } else if (e.target.type === 'checkbox') {
                this.toggleTarea(e.target.dataset.id);
            }
        });
        
        this.botonLimpiar.addEventListener('click', () => {
            this.limpiarCompletadas();
        });
    }
    
    cargarTareas() {
        let guardadas = localStorage.getItem('tareas');
        return guardadas ? JSON.parse(guardadas) : [];
    }
    
    guardarTareas() {
        localStorage.setItem('tareas', JSON.stringify(this.tareas));
    }
    
    agregarTarea() {
        let texto = this.input.value.trim();
        
        if (texto) {
            let tarea = {
                id: Date.now(),
                texto: texto,
                completada: false
            };
            
            this.tareas.push(tarea);
            this.guardarTareas();
            this.renderizar();
            this.input.value = '';
        }
    }
    
    eliminarTarea(id) {
        this.tareas = this.tareas.filter(t => t.id != id);
        this.guardarTareas();
        this.renderizar();
    }
    
    toggleTarea(id) {
        let tarea = this.tareas.find(t => t.id == id);
        if (tarea) {
            tarea.completada = !tarea.completada;
            this.guardarTareas();
            this.renderizar();
        }
    }
    
    limpiarCompletadas() {
        this.tareas = this.tareas.filter(t => !t.completada);
        this.guardarTareas();
        this.renderizar();
    }
    
    renderizar() {
        this.lista.innerHTML = '';
        
        this.tareas.forEach(tarea => {
            let li = document.createElement('li');
            li.innerHTML = `
                <input type="checkbox" 
                       data-id="${tarea.id}" 
                       ${tarea.completada ? 'checked' : ''}>
                <span class="${tarea.completada ? 'completada' : ''}">
                    ${tarea.texto}
                </span>
                <button class="eliminar" data-id="${tarea.id}">X</button>
            `;
            this.lista.appendChild(li);
        });
    }
}

// Inicializar cuando el DOM esté listo
document.addEventListener('DOMContentLoaded', () => {
    new ListaTareas();
});
```

## Recursos para Continuar Aprendiendo

- [MDN JavaScript](https://developer.mozilla.org/es/docs/Web/JavaScript)
- [JavaScript.info](https://javascript.info/)
- [Eloquent JavaScript](https://eloquentjavascript.net/)
- [You Don't Know JS](https://github.com/getify/You-Dont-Know-JS)
- [JavaScript30](https://javascript30.com/) - 30 proyectos en 30 días

JavaScript es un lenguaje muy poderoso y está en constante evolución. Lo que vimos aquí son los fundamentos, pero hay mucho más por explorar. La clave está en practicar constantemente, construir proyectos y no tener miedo a experimentar.

Recuerden: los errores son parte del proceso de aprendizaje. Cada error es una oportunidad para entender mejor cómo funciona JavaScript. Usen la consola, debuggeen su código, y sobre todo, diviértanse programando.