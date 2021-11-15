---
title: JavaScipt para React.js - Parte 2
date: "2021-11-10" 
description: "Repaso sobre los conceptos fundamentales de JavaScript para trabajar con React.js: Variables"
---
<!-- date: año-mes-día -->

Contenido de este post:

1. Spread Operator
2. Rest Operator & Destructuring
3. Métodos: map, filter, reduce
4. fetch API

# 1. Spread Operator

- El Spread Operator nos permite tomar valores qué se encuentran dentro una estructura de datos array [] o object {} y esparcirlos dependiendo del contexto.
- El Spread Operator hace una copia de los datos, lo que permite trabar sin mutar los datos originales

## Spread Operator en Arrays
 ```js
const fn = (a,b,c) => console.log(a + b + c);

let arr = [1,2,3];

fn(arr[0], arr[2], arr[2]); // Viaja manera: 6
fn(..arr); // Usando el Spread Operator: 6

/*
El spread operator lo que hara es mapear y copiar cada elemento del array y los va a poner como parametros según la función las tenga.
*/
```

## Concatenar datos usando el Spread Operator

```js
const arr1 = [1,2,3,4];
const arr2 = [5,6];

const arr3 = arr1.concat(arr2); // Vieja manera imprimira: [1,2,3,4,5,6]
const arr4 = [...arr1, ...arr2]; // Usando el Spread Operator: [1,2,3,4,5,6]
const arr5 = [...arr1, ...arr2, 7, 8]; // Usando el Spread Operator: [1,2,3,4,5,6,7,8]
```
## Spread Operator en Objetos literales

```js
const obj = {
  a: 1,
  b: 2
}
const obj2 = {
  b: 5,
  c: "Chanchito feliz"
}

```

## Parametro vs Argumento
- Los Parametro son lo que se indican en la declaración de la función 
```js
const fn = (a,b,c) => console.log(a + b + c);
```
- Los Argumentos son los que se indican en la llamada a la función
```js
fn(..arr);
```

# 2. Rest Operator & Destructuring

Un Rest Operator visualmente es muy similar a un Spread Operator pero se usa en un contexto diferente.
```js
const rest = (...argumentos) => {
  console.log(argumentos);
}
rest(1,2,3); // [1,2,3]
```
Cuando usamos el Rest Operator como argumentos (Function o Arrow Function) tomamos todos los argumentos que le estamos pasando en el monento de llamar la functión y los estamos empaquetando en un arreglo.
El Parametro Rest Operator que usemos en una funcuón siempre debe ir al final.
Tambien puedo tomar un valor por un lado y los demás valores en otro:
```js
const rest = (1, ...argumentos) => {
  console.log(a); // a asociado al primer valor
  console.log(argumentos); // El resto de los argumentos que no lo asignamos a una variable
}
rest(1,2,3); 
/*
1
[2,3]
*/ 
```

## Object Destructuring

```js
const obj = {
  a: 1,
  b: 2,
  c: 3,
  d: 4,
  e: 5
}

const {a} = obj; //Destructuración para obtener el valor asociado a la llave a: 1
const {b} = obj; //Destructuración para obtener el valor asociado a la llave a: 2
const {c} = obj; //Destructuración para obtener el valor asociado a la llave a: 3
const {a,b, c} = obj; //Destructuración para obtener el valor asociado a la llave a: 1 2 3
const {d } = obj; //Destructuración para obtener el valor asociado a la llave a: 4
const {a,b, ...restObj } = obj; //Destructuración para obtener el valor asociado a la llave a: 1 2 {c: 3, d: 4 }  restObj = {c: 3, d: 4 }
```

# 3. Métodos: map, filter, reduce
...

# 4. fetch API
