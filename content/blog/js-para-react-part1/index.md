---
title: JavaScipt para React.js - Parte 1
date: "2021-11-10" 
description: "Repaso sobre los conceptos fundamentales de JavaScript para trabajar con React.js: Variables"
---
<!-- date: año-mes-día -->

Contenido de este post:

1. Variables en JS: Var, let y const
2. Functions & Arrow functions
3. Export e import
4. Clases

# 1. Variables

## ¿Qué es una Variable en JavaScript?
En JavaScript las variables son un **hilo nombrado qué vinculan** datos o información con un fragmento de memoria. Las variables pueden ser declaradas, asignadas o creadas y así mismo serán sus formas de escribirlas: 
- Declaración de variable: palabra_clave nombre_variable; 
- Asignación de variable: nombre_variable = dato o información
- Creación de variable: palabra_clave nombre_variable = dato o información;

## ¿Cómo se accede al datos o información de una variable?
Para utilizar o simplemente ver el dato o información vinculada a cierta variable, hacemos el llamada al nombre de la variable.

## ¿Cuantos tipos de variables existen en JavaScript?

En JavaScript existen 3 tipos de variables identificads con las siguientes palabras claves:
- var (Antes del ES6)
- let (Depues del ES6)
- const (Depues del ES6)

### var

Cuando creamos una variable usando la palabra clave **var**, el compilador de JS siempre divide la variable creada en dos partes: 
- La declaración de la variable, qué la ubica al inicio del archivo
- La asignación de la variable, qué la deja donde fue creada.

Veamos un ejemplo visual para entender lo anterior:

```js
var variableVar = "variable con var"; // linea 50
```

```js
var variableVar; // linea 1
/*
lineas de código...
*/
variableVar = "variable con var"; // linea 50
```
El anterior comportamiento se llama **Hoisting** y a lo largo de la historia del desarrollo web ha generado dificultades de varios tipos, razones por las cuales se crearon las palabras claves **let & const**.
Actualmente usar var se puede considerar una mala práctica. 

### let
- let es similar a var con la diferencia de qué no experimenta Hoisting.
- A let **si** le puede reasignar valores. 

### const
- const tampoco experimenta Hoisting. 
- A const **no** se le puede reasignar valores.

# 2. Functions & Arrow functions

## Function

Para entender las Arrow function es necesario hablar tambien de las funciones literales y asñi ver sus diferencias.

Las funciones declaradas con la plabra clave **_function:_**
- Son funciones querelizan tareas
- Se pueden guardar en una variable
- Sirven tambien como una especie de clases.
JavaScript al ser un lenguaje multiparadigma, este tambien implementa la herencia basada en prototipos.

### Funciones declaradas
```js
function fn(){
  return "jorge feliz";
}

console.log(fn()); // Opción A

const r = fn();
console.log(r); // Opción B
```

### Llamando una función con la palabra reservada new
```js
function fn(){
  return "jorge feliz";
}

const r = new fn(); //Se crea una instancia de la función, cómo si fuera una clase
console.log(r);
```
Al hacer una llamada a una función con la palabra reservada _**new**_ pasan cuatro cosas:
1. Se crea un objeto literal desde la nada jajaj sí, desde la nada. **{}**
2. El objeto literal empieza a tomar todas las porpiedades que nosotros le asignemos mediante la plabra reservada **this**
3. Va a ignorar por completo el return que nosotros le indiquemos a la función y lo que va a retornar de manera implicita es **this**
4. El prototpo de las funciones se le está asignando al valor de _**this**_ que nosotros estamos retornando.

Las funciones creadas con la plabra clave **_function_** tiene un contexto de _**this**_

```js
function fn(){
  this.props = "propiedad usando this.prop"
  return "jorge feliz";
}

const r = new fn();
console.log(r);
```

Aquí posiblement te este preguntando...pero nosotos tenemos una plabra reservada _**class**_ despues del ES6 para usar clases en javaScript. La verdad es que la palabra reservada _**class**_ es unica y exclusivamente azucar sintactica. Por debajo lo que hace esa palabra es crear una función de la manera previamente vista.

Todas las funciones qué nosotros declaremos con la palabra reservada _**function**__ pueden cumplir con dos objetivos:
1. Ser una función
2. Puede tener un contexto _**this**_ y podemos utilizarlas para implementar herencia basada en prototipos en JavaScript.

> Las funciones además de ser funciones también son clases en JavaScript basadas en prototipo que tiene como nombre la palabra _**function.**_


## Arrow Funtions

La declaraciónnde una función flecha es con parentesis seguido de un signo de igualdad y mayor que, finalizando con las llaves. Y toda guardarla en una variable o una constante. Sintaxis de una Arrow function:
```js
const fatFn = () => {
  return "jorge feliz";
};

const r1 = fatFn(); // Así se hace el llamado a una función flecha
```

Las fat Arrow Function qué no tegan las llaves, tiene un return implicito.
```js
const fnR = () => 2; // <- Si trabaja

const fnR = () => {
  2
}; // <- No trabaja
```


### Diferencias entre Fat Arros Function vs Functions
- ¿Pueden ser llamadas con la palabra reservada _**new**_? Las fat Arrow Functions no y las Functions si.
- ¿Pueden funcionar cómo clases y tener contexto _**this**_? Las fat Arrow Functions no y las Functions si.
- ¿Tienen un Return implicito? Las fat Arrow Functions si y las Functions no.
 

# 3. Export e Import

En JavaScript una forma de reutilizar código escrito es usando las palabras reservadas _**Export e Import**_

Hay dos métodos de importar y exportar funcionalidades entre archivos:
1. **Export default** 
```js
// Archivo desde donde exporto
const nombres = [jorge, carolina];

export default nombres;
```
```js
// Archivo desde donde importo
import CualquierNombre from './folderName/fileName';

console.log(CualquierNombre);
```

2. **Export literal**
```js
// Archivo desde donde exporto
const nombres = [jorge, carolina];

export { nombres };
```
```js
// Archivo desde donde importo
import { nombres } from './folderName/fileName';

console.log( nombres);
```

# 3. Clases

## Expresión de clase

Una expresión de clase se crea usando la palabra reservada **_class_** y posterormente asignandola a una variable, pueden ser nombradas:

```js
const Rectangulo = class R { // Esto se conoce como una Expresión de clase

}

const r = new Rectangulo(); //Así creamos una instancia de la clase R, que esta asignada a la variable Rectangulo
```
o pueden ser anonimas:

```js
const Rectangulo = class { // Esto se conoce como una Expresión de clase

}

const r = new Rectangulo(); //Así creamos una instancia de la clase R, que esta asignada a la variable Rectangulo
```

## Declaración de clase con la plabara reservada _Class_

Una declaración de clase se crea usando la palabra reservada **_class_** solamente.

```js
class Rectangulo { // Esto se conoce como una Declaración de clase

}

const r = new Rectangulo(); //Así creamos una instancia de la clase R, que esta asignada a la variable Rectangulo
```

## Declaración de clase con la plabara reservada _Function_

```js
function Cuadrado (){};

const c = new Cuadrado();
```

Cada vez que hagamos una llamada a una clase con la palabra reservada **_new_** (Crear una instancia de la clase). Se ejecutara siempre el cosntructor.

```js
class Chancho {
  constructor(){
    console.log("Soy un chancho");
  }
}

const Feliz = new Chancho; // Imprimira: Soy un chancho
const Triste = new Chancho; // Imprimira: Soy un chancho
const Alegre = new Chancho; // Imprimira: Soy un chancho
```

A la cunción constructor se le pueden pasar propiedades como parametros, por ejemplo:
```js
class Chancho {
  constructor(estado){
    console.log(`Soy un chancho ${estado}`);
  }
}

const Feliz = new Chancho("feliz"); // Imprimira: Soy un chancho feliz
const Triste = new Chancho("triste"); // Imprimira: Soy un chancho triste
const Alegre = new Chancho("alegre"); // Imprimira: Soy un chancho alegre
const Alegre = new Chancho(); // Imprimira: Soy un chancho undefined
```
Para genera valores por defecto se puede asignar valores por defecto a los arguentos:
```js
class Chancho {
  constructor(estado = "Feliz"){
    console.log(`Soy un chancho ${estado}`);
  }
}

const Feliz = new Chancho("feliz"); // Imprimira: Soy un chancho feliz
const Triste = new Chancho("triste"); // Imprimira: Soy un chancho triste
const Alegre = new Chancho("alegre"); // Imprimira: Soy un chancho alegre
const Alegre = new Chancho(); // Imprimira: Soy un chancho Feliz
```
Tambien se pueden pasar valores en las Clases a traves de sus propiedades
```js
class Chancho {
  estado = "Feliz";
  constructor(){
    console.log(`Soy un chancho ${this.estado}`);
  }
}

const Feliz = new Chancho("feliz"); // Imprimira: Soy un chancho Feliz
const Triste = new Chancho("triste"); // Imprimira: Soy un chancho Feliz
const Alegre = new Chancho("alegre"); // Imprimira: Soy un chancho Feliz
const Alegre = new Chancho(); // Imprimira: Soy un chancho Feliz
```

A las clases tambien se les puede agregar métodos:
```js
class Chancho {
  propiedad = "mi propiedad"
  constructor(estado = "Feliz"){
   this.estado = estado
  }

  hablar(){
     console.log(`Soy un chancho ${this.estado}`);
  }
}

const Feliz = new Chancho("feliz"); // Imprimira: Soy un chancho Feliz
console.log(Feliz); // Chancho {propiedad: "mi propiedad", estado: "Feliz"}
console.log(Feliz.__proto__);
const Triste = new Chancho("triste"); // Imprimira: Soy un chancho Feliz
const Alegre = new Chancho("alegre"); // Imprimira: Soy un chancho Feliz
const Alegre = new Chancho(); // Imprimira: Soy un chancho Feliz
```

## Diff Class vs Function

1. Class = Azucar sintactica que debajo genera una function vs Function = a una función directamente
2. function presenta Hoisting como Var. Class no tienen Hoisting
3. Con Class solo se puede generar una instancia usando la palabra reservada **_new_**


## Nueva funcionalidad de las clases de JS: Propiedades privadas
- Solo se pueden acceder desde adentro de una instancia de una clase creada con la palabra _new_
- 

Para indicar una propiedad privada en una clase, se usa el signo númeral antes del nombre de la propiedad.

```js
class Chancho {
  propiedad = "mi propiedad"
  #hasHambre = false
  constructor(estado = "Feliz", hasHambre = false){
   this.estado = estado
   this.#hasHambre = hambre
  }

  hablar(){
     console.log(`Soy un chancho ${this.estado} ${this.#hasHambre ? "con mucha hambre!" : "satisfecho"}`);
  }
}

const Feliz = new Chancho("feliz"); // Imprimira: Soy un chancho Feliz
feliz.hablar(); // Imprime: soy un chancho feliz satisfecho
```
Las variables privadas de la clase solo podran ser accedida desde las instancias de la clase.

## Nueva funcionalidad de las clases de JS: Métodos estaticos
- Un método estatico es aquel que solo se puede acceder desde la clase y no es necsario generar una instancia.
- Seutiliza la palabra reservas **_static_**
- Los métodos estaticos no pueden acceder a las propiedads de una clase. Prque las propuedades pertenecen a una clase, pública o privada. 
- La única manera que desde un método se pueda acceder a una propiedad, es que esa propiedad sea estatica tabiem. Esto se hace usando la palabra reservada **_static_**  antes del nombre de la propiedad

```js
class Chancho {
  propiedad = "mi propiedad"
  #hasHambre = false
  static estatico = 42
  constructor(estado = "Feliz", hasHambre = false){
   this.estado = estado
   this.#hasHambre = hambre
  }

  hablar(){
     console.log(`Soy un chancho ${this.estado} ${this.#hasHambre ? "con mucha hambre!" : "satisfecho"}`);
  }
  static comer(){
     console.log(this, this.estatico,`Estoy comiendo!`);
  }
}

Chancho.comer(); // 42 Estoy comiendo!
```