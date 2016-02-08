# Clase 4

### t3chfest (11/02 y 12/02)

![t3chfest_logo](https://t3chfest.uc3m.es/static/resources/media/rrss.png)

- [Programa de charlas](https://t3chfest.uc3m.es/programa/)
- [Entradas gratuitas](https://t3chfest2016.eventbrite.es/)

### Caracteres especiales:
```javascript
    /*
    \t -> Tabulador
    \' -> Comillas Simples
    \" -> Comillas Dobles
    \\ -> \
    \n -> Salto de línea
    */

    function caracteresDemo () {
    console.log("Hasta aquí... todo correcto. Ahora vamos a \"tabular\":\tves? Ya estamos más lejos.\n\'Otra linea ;-)\'")
    };
```

### Ejercicios

**Recuerda:** Utiliza [JSHint](http://jshint.com/) para detectar errores..

**1 -** Utiliza .assert para controlar cuando se muestra tu nombre por consola.
```javascript
	var controlador = false;
	console.assert(controlador,  "Hola, yo soy Ulises Gascón");
```

**2 -** Crea un script que nos permita calcular el tiempo que se necesita para realizar la siguientes acciones.
- Especificaciones:
	- Imprimir tu nombre usando **console.log, console.info, console.warn**
```javascript
	var nombre = "Hola, yo soy Ulises Gascón";
	console.time("presentación");
	console.log(nombre);
	console.info(nombre);
	console.warn(nombre);
	console.timeEnd("presentación");
```

**3 -** Partiendo del ejercicio anterior mejora los estilos de cada mensaje usando estilos.
```javascript
	var nombre = "Hola, yo soy Ulises Gascón";
	console.time("presentación");
	console.log("%c %s", "background: black; color: #FFF; font-size:20px;" ,nombre);
	console.info("%c %s", "background: #3EBDFF; color: #FFF; font-size:20px;" ,nombre);
	console.warn("%c %s", "background: #FFAA00; color: #FFF; font-size:22px;" ,nombre);
	console.timeEnd("presentación");
```

**4 -** Agrupa cada tipo de mensaje y añade un contador de tiempo por cada grupo.
```javascript
	var nombre = "Hola, yo soy Ulises Gascón";
	console.time("presentación");
	
	// console.log
	console.group("grupo console.log");
	console.time("tiempo grupo console.log");
	console.log("%c %s", "background: black; color: #FFF; font-size:20px;" ,nombre);
	console.timeEnd("tiempo grupo console.log");
	console.groupEnd();
	
	
	// console.info
	console.group("grupo console.info");
	console.time("tiempo grupo console.info");
	console.info("%c %s", "background: #3EBDFF; color: #FFF; font-size:20px;" ,nombre);
	console.timeEnd("tiempo grupo console.info");
	console.groupEnd();
	
	
	// console.warn
	console.group("grupo console.warn");
	console.time("tiempo grupo console.warn");
	console.warn("%c %s", "background: #FFAA00; color: #FFF; font-size:22px;" ,nombre);
	console.timeEnd("tiempo grupo console.warn");
	console.groupEnd();
	
	
	console.timeEnd("presentación");
```

**5 -** Crea una tabla usando la consola para mostrar el nombre de tus compañeros y el puesto que ocupa en la clase.
```javascript
    var alumnos = [
	     { nombre: "Juan", puesto: 1 },
	     { nombre: "Oscar", puesto: 2 },
	     { nombre: "Paul", puesto: 3 },
	     { nombre: "Nuria", puesto: 4 },
	     { nombre: "Noemi", puesto: 5 }
	     { nombre: "Oliver", puesto: 6 }
	 ];
	 
	 console.table(alumnos);
```



### Comentarios
- Una línea
```javascript
// Comentario en una línea
```
- Multiples Líneas
```javascript
/*
Una Línea....
Otra linea...
Etc...
*/
```
- [JSDoc](https://en.wikipedia.org/wiki/JSDoc)

### Variables

- No se pueden usar espacios
```javascript
var con espacios = 1;
```

- No usar un número delante
```javascript
var 1numero = 1;
```

- Válidos, pero no recomendado
```javascript
var con_guiones_bajos = 1;
var dame$ = 1;
```

- Válidos, es mejor usar [camelCase](https://es.wikipedia.org/wiki/CamelCase)
```javascript
var otraOpcion = 1;
var opcionCon123123 = 1;
```


### Tipos de variables

Operador *typeof* y su [especificación](http://www.ecma-international.org/ecma-262/5.1/#sec-11.4.3)

- [x] Undefined
```javascript
typeof undefined
typeof noDefinido
typeof tampocoCreado
```

- [x] Object
```javascript
typeof null
typeof [15, 4]
typeof new Date()
typeof {a:1}
```

- [x] Boolean
```javascript
typeof false
typeof true
typeof Boolean(false)
```

- [x] Number
```javascript
typeof 3
typeof 3.14
typeof NaN
typeof Infinity
```

- [x] String
```javascript
typeof "hola"
```

- [x] Function
```javascript
typeof function(){}
```


### Matemáticas Básicas
```javascript
var suma = 5 + 4;
var resta = 10 - 6;
var multiplicacion = 3 * 3;
var division = 6 / 2;
var modulo = 43 % 10;

function calcular (operacion) {
    console.log(operacion);
};
```

### Matemáticas Básicas (Agrupando operaciones)
```javascript
var expresion1 = (3 + 7) * 10;
var expresion2 = (-56 * 6) - 74 * -25;
var expresion3 = (3 * 3) + 10 - 12 / 2;
var expresion4 = 44 + (83 % (33 + 100));
var expresion5 = -145 + (500 / 10 - 5) + 10 * 10 ;

function calcular (operacion) {
    console.log(operacion);
};
```

### Matemáticas Básicas (crecimiento y decrecimiento)
```javascript
var numero = 5;

console.log(--numero); // 4
console.log(numero--); // 5 (luego 4)
console.log(++numero); // 6
console.log(numero++); // 5 (luego 6)
```

### Operadores de asignación
- = *Asignacion*
```javascript
var x = 1;
var y = 2;
x = y;
console.info("\"x\" vale ", x);
```

- += *Suma*
```javascript
var x = 1;
var y = 2;
x += y;
console.info("\"x\" vale ", x); // x = x + y
```

- -= *Resta*
```javascript
var x = 1;
var y = 2;
x -= y;
console.info("\"x\" vale ", x); // x = x - y
```

- *= *Multiplicación*
```javascript
var x = 1;
var y = 2;
x *= y;
console.info("\"x\" vale ", x); // x = x * y
```

- /= *División*
```javascript
var x = 1;
var y = 2;
x /= y;
console.info("\"x\" vale ", x); // x = x / y
```

- %= *Resto*
```javascript
var x = 1;
var y = 2;
x %= y;
console.info("\"x\" vale ", x); // x = x % y
```


**Jugando con variables**

```javascript
var empezoComo3 = 3;
era3();

empezoComo3 = 35;
era3();

empezoComo3 = empezoComo3 + 30;
era3();

empezoComo3 += 4;
era3();

empezoComo3++;
era3();

empezoComo3 -= 12;
era3();

empezoComo3--;
era3();

empezoComo3 *= 10;
era3();

empezoComo3 /= 11;
era3();

empezoComo3 += "texto";
era3();

empezoComo3 += 20;
era3();

empezoComo3++;
era3();


function era3 () {
    console.log("empezoComo3 debería ser 3, ahora su valor es " + empezoComo3);
};
```


### Interacción Básica con el Usuario

- alert():
    ```javascript
    alert("¡Bienvenido a esta web!");
    ```

- confirm():
    ```javascript
    confirm("¿Esta seguro que desea abandonar esta web?");
    ```


- Ejemplo:
    ```javascript
    var respuesta = confirm("presiona un botón!");
    if (respuesta === true) {
        console.log("Has aceptado!");
    } else {
        console.log("Has cancelado");
    }
    ```

- prompt():
    ```javascript
    prompt("¿Como te llamas?");
    ```

- Registremos los datos en una variable:
    ```javascript
    var nombre = prompt("¿Como te llamas?");
    ```

### Ejercicios

**1 -** Vamos a solicitar la colaboración del usuario para lograr nuestros objetivos:
- Objetivos:
	-  Captura el nombre del usuario usando prompt
	-  Pregunta al usuario si desea *"comprobar lo rápido que funciona su navegador"*.
	-  En caso afirmativo imprimiremos el nombre del usuario por consola aplicandole estilos y calculando el tiempo que tarda en realizar la operación
- En caso negativo mostraremos un *alert* informativo.
```javascript
    // Tu solución
```

### Modo Estricto
> El modo estricto hace varios cambios en la semántica normal de JavaScript. Primero, modo estricto elimina algunos errores silenciosos de JavaScript cambiando a que lance los errores. Segundo, modo estricto corrige errores que hacen que sea difícil para los motores de JavaScript para realizar optimizaciones: código de modo estricto a veces se puede hacer para correr más rápido que el código idéntico que no es estricto. Tercero, el modo estricto prohíbe sintaxis que es probable que sea definida en futuras versiones de ECMAScript.
> - [Mozilla](https://developer.mozilla.org/es/docs/Web/JavaScript/Referencia/Modo_estricto)

- [Compatibilidad](http://caniuse.com/#feat=use-strict)

En resumen:
- Detectaremos más errores
- Mejora la interpretación, lo que aumenta la velocidad de ejecucción.
- Previene que usemos sintaxis de futuras versiones de ECMAScript.

Aplicándolo a todo nuestro código

```javascript
// ./script.js
(function() {
  "use strict";

  // Nuestro código

})();
```

Aplicándolo solo en parte del código
```javascript
// ./script.js
function estricta(){
  'use strict';
  function anidada() {
      return "Yo también!";
  }
  return "Hola! Soy una función en modo estricto!  " + anidada();
}

function noEstricta() {
    return "yo no soy una función estricta.";
}
```

Algunos ejemplos:

- Error: Usar variables u objetos sin declararlos antes.

```javascript
    function estricto(){
        'use strict';
        pi = 3.14;
        console.log(pi);
    }
```

- Error: Borrar variables, objetos o funciones. 

```javascript
    function estricto(){
        'use strict';
        pi = 3.14;
        delete pi
    }
```

- Error: Duplicar parámetros

```javascript
    function estricto(){
        'use strict';
        function x (p1, p1){
            // código
        }
    }
```

- Error: Al usar carácteres escapados
 
```javascript
    function estricto(){
        'use strict';
        var x = \010; 
    }
```

Error: Al usar *writable:false*

```javascript
    function estricto(){
        'use strict';
        var obj = {};
        Object.defineProperty(obj, "x", {value:0, writable:false});
        obj.x = 3.14;
    }
```

Error: Al usar *with* 

```javascript
    function estricto(){
        'use strict';
        with(document.getElementById('elemento').style) {
            backgroundColor = 'black';
            color = 'red';
            font_Size = '32px'; // Crea una variable global
        }
    }
```

Error: Al usar *eval()* por seguridad

```javascript
    function estricto(){
        'use strict';
        eval ("var x = 2");
        console.log(x);
    }
```



Otras palabras reservadas en modo estricto:
- implements
- interface
- let
- package
- private
- protected
- public
- static
- yield


**Ejercicios:**

1 - Diseña un algoritmo que lea dos números y realice los siguientes cálculos:
- Valor de su suma
- Valor de su resta
- Valor de su division
- Valor de su producto

```javascript
    // Tu solución
```

2 - Diseña un algoritmo para calcular el porcentaje de hombres y mujeres en nuestro curso.
- Trucos:
	- Calcular porcentajes (segmento*100)/total

```javascript
	// Tu solución
```


### Comparadores básicos

```javascript
var mayorQue = 100 > 10;
var menorQue = 10 < 100;
var mayorIgual = 100 >= 10;
var menorIgual = 10 <= 100;
var igual = 10 == 10;
var igualTotalmente = 10 === 10;
var noIgual = 100 != 10;

function comparar (dato) {
    console.log(dato);
};
```


### Comparadores complejos
- **AND(&&)**
```javascript
    var comparacion;
    comparacion = true && true; // true
    comparacion = true && false // false
    comparacion = false && false // false
    comparacion = false && true // false
```

- **OR(||)**
```javascript
    var comparacion;
    comparacion = true || true; // true
    comparacion = true || false // true
    comparacion = false || false // false
    comparacion = false || true // true
```

- Ejemplos:
```javascript
var ex1 = true && true; // true
var ex2 = (2 == 2) && (3 >= 6); // false
var ex3 = (2>3) || (17 <= 40); // true
var ex4 = false || false; // false

function condicionalAvanzado ( paraComparar ) {
    if (paraComparar) {
        console.log("Verdadero!");
    } else {
        console.log("falso!");
    };
};
```

### Otros datos

- Valor *real* es *true*:
```javascript
console.log("valor boleano de \"Fictizia\":", Boolean("Fictizia")  );
console.log("valor boleano de 1235:", Boolean(1235));
console.log("valor boleano de -1235:", Boolean(-1235));
console.log("valor boleano de un objeto:", Boolean({saludo: "hola"}));
console.log("valor boleano de un array:", Boolean(["platano", -1, false]));
console.log("valor boleano de un array:", Boolean(function(){}));
```

- Sin valor *real* es *false*:
```javascript
console.log("valor boleano de \"\":", Boolean("")  );
console.log("valor boleano de 0:", Boolean(0));
console.log("valor boleano de -0:", Boolean(-0));
console.log("valor boleano de null:", Boolean(null));
console.log("valor boleano de undefined:", Boolean(undefined));
console.log("valor boleano de NaN:", Boolean(NaN));
```


### If... else

- Estructura:
    ```javascript
    /* IF ...ELSE
    if (-algo verdadero-) {
        -ejecutaremos este código-
    } else {
        -Si lo anterior no era verdadero, se ejecutara este código-
    };
    */
    ```

- Documentación:
    - [If... else en w3schools](http://www.w3schools.com/js/js_if_else.asp)
    - [If... else en MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/if...else)

- Ejemplo:
    ```javascript
    if (true) {
        console.log("true, por eso me ejecuto");
    } else {
        console.log("false, por eso me ejecuto");
    }
    ```


### Else if...

```javascript
function testCondiccion (condicion){
    if (condicion == 1) {
        console.log("1, por eso me ejecuto");
    } else if (condicion == 2){
        console.log("2, por eso me ejecuto");
    } else {
        console.log("no es 1 o 2, por eso me ejecuto");
    }
}
```


### Switch

- Estructura:
    ```javascript
    /* Switch
	switch(expresión) {
	    case n:
	        //Código
	        break;
	    case n:
	        //Código
	        break;
	    default:
	        //Código
	}
    */
    ```

- Documentación:
    - [Switch en w3schools](http://www.w3schools.com/js/js_switch.asp)
    - [Switch en MDN](https://developer.mozilla.org/es/docs/Web/JavaScript/Referencia/Sentencias/switch)

- **Casos únicos:**
    ```javascript
	var nombre = "";
	switch (nombre) {
	  case "Pepe":
	    console.log("Hola Pepe");
	    break;
	  case "Luis":
	    console.log("Hola Luis");
	    break;
	  case "Antonio":
	    console.log("Hola Antonio");
	    break;
	  default:
	    console.log('Ninguno de los nombres que pensamos... es '+nombre);
	}
    ```

- **Multiples coincidencias:**
    ```javascript
	var nombre = "";
	switch (nombre)
	{
	   case "Pepe":
	   case "Luis":
	   case "Antonio":
	       alert('Hola '+nombre);
	       break;

	   default:
	       console.log('Ninguno de los nombres que pensamos... es '+nombre);
	}
    ```

### Operador Ternario (?:)

- Estructura:
    ```javascript
    /* 
    -- Una operación por caso --
	condicion ? expresion1 : expresion2 
    
    -- Multiples Operaciones por caso --
	condicion ? (
		operacion1,
		operacion2,
		otraoperacion
	) : ( 
		operacion1,
		operacion2,
		otraoperacion
	);

    -- Evaluaciones multiples --
    	condicion ? expresion1 : condicion2 ? expresion1 : expresion2;
    */
    ```

- Una operación por caso:
```javascript
	var esMiembro = true;
	console.info("El pago son  " + (esMiembro ? "20.00€" : "50.00€"));
```

- Evalución múltiple:
```javascript
	var esMiembro = true;
	var esAdulto = true;
	console.info(esMiembro ? "El pago son 20.00€" : esAdulto ? "Puedes enviar la solicitud cuando quieras" : "Tines que esperar aún. Lo siento.");
```

- Múltiples Operaciones:
```javascript
	var mensaje,
	esMiembro = true;
	
	esMiembro ? (
		mensaje = "El pago son 20.00€",
		console.info(mensaje)
	) : (
		mensaje = "El pago son 50.00€",
		console.info(mensaje)
	);
```

**Ejercicios:**

Realiza los siguientes ejercicios usando en cada uno los tres tipos de condicionales (If...else, Switch, operador ternario )

**1 -** Diseña un algoritmo que lea dos números y los compare. Como resultado esperamos que nos diga cual es mayor... o si son iguales.

- Usando *if...else*
```javascript
    // Tu solución
```

- Usando *Operador Ternario (?:)*
```javascript
    // Tu solución
```

- Usando *Switch*
```javascript
    // Tu solución
```

**2 -** Diseña un algoritmo que lea tres números distintos y nos diga cual de ellos es el mayor.

- Usando *if...else*
```javascript
    // Tu solución
```

- Usando *Operador Ternario (?:)*
```javascript
    // Tu solución
```

- Usando *Switch*
```javascript
    // Tu solución
```


**3 -** Diseña un algoritmo que siga el siguiente proceso:
- Si el primero es negativo, debe sumar los otros dos
- Sino multiplicará los tres numeros
- Mostrar el resultado final incluyendo una referencia a la operación realizada.

- Usando *if...else*
```javascript
    // Tu solución
```

- Usando *Operador Ternario (?:)*
```javascript
    // Tu solución
```

- Usando *Switch*
```javascript
    // Tu solución
```

**4 -** Diseña un algoritmo que aplique al precio de un producto un descuento cuando se den las siguientes caracteristicas.
- Se aplica un 25% cuando:
	- Estamos en los meses de invierno
	- Y no es viernes o fin de semana.

- Usando *if...else*
```javascript
    // Tu solución
```

- Usando *Operador Ternario (?:)*
```javascript
    // Tu solución
```

- Usando *Switch*
```javascript
    // Tu solución
```

**5 -** Diseña un algoritmo que al introducir un numero por teclado. Que nos diga si es positivo o negativo.

- Usando *if...else*
```javascript
    // Tu solución
```

- Usando *Operador Ternario (?:)*
```javascript
    // Tu solución
```

- Usando *Switch*
```javascript
    // Tu solución
```


**6 -** Diseña un algoritmo que al introducir un número por teclado. Que nos diga si es par o impar.

- Usando *if...else*
```javascript
    // Tu solución
```

- Usando *Operador Ternario (?:)*
```javascript
    // Tu solución
```

- Usando *Switch*
```javascript
    // Tu solución
```


**7 -** Diseña un algoritmo que nos confirme si un [año es bisiesto](https://es.wikipedia.org/wiki/A%C3%B1o_bisiesto) o no.
- Caracteristicas de un año bisiesto:
	- Tiene que ser divisible entre 4
	- No tiene que ser divisible entre 100
	- Puede ser divisble entre 100 y entre 400

- Usando *if...else*
```javascript
    // Tu solución
```

- Usando *Operador Ternario (?:)*
```javascript
    // Tu solución
```

- Usando *Switch*
```javascript
    // Tu solución
```