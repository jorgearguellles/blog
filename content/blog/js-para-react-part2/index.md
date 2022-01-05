---
title: JavaScipt para React.js - Parte 2
date: "2021-11-09" 
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

## filter
**Filter** toma los valores de un arreglo base y devuelve un nuevo arreglo solo con los elementos que evaluen a **_true_**

- Filter retorna un nuevo arreglo con la misma o menor longitud qué el arreglo base.
- El nuevo arreglo solo contiene los elementos del arreglo base que evaluen **_true._**
- Filter va elemento por elemento del arreglo verificando qué se cumpla la condición expresada.
- 

```js
const arr = [0,1,2,3,4];

const r = arr.filter( el => el > 2); 
console.log(r); // [3,4]

const r = arr.filter( el => el < 2); 
console.log(r); // [0,1]
```

EL metodo Filter puede recibir otro parametro:
```js
const arr = [5,1,2,3,4];

const r = arr.filter( (el, i) => {
  console.log("Indice:",i);
  return el > 2;
}); 
console.log(r);

```
## map

**map** toma todos los elementos que se encuentra dentro de un arreglo y les aplica una función, finalmente devuelve un arreglo de la misma longitud pero con una funcion aplicada a cada uno de los elementos.

```js
const arr = [5,1,2,3,4];

const mapped = arr.map( el => el * 2);
console.log(mapped); // [10,2,3,6,8]

const users = [
  { id: 1, name: "Jorge"},
  { id: 2, name: "Juan"},
  { id: 3, name: "Javier"},
  { id: 4, name: "Julian"},
  { id: 5, name: "Jordan"},
];

const usersMapped = users.map( user => `
  <h1>${user.name}</h1>
  <p>${user.id}</p>
  `);
console.log(usersMapped); 
```
## Redece

**reduce** Toma todos los elementos de un arreglo y retorna lo que queremos en un elemento: Un arreglo, Un Número

```js

const arr = [5,1,2,3,4];
const arrNeg = [-5,-1,-2,-3,-4];
const users = [
  { id: 1, name: "Jorge"},
  { id: 2, name: "Juan"},
  { id: 3, name: "Javier"},
  { id: 4, name: "Julian"},
  { id: 5, name: "Jordan"},
];

// const r1 = arr.reduce(Función accumuladora, Valor inicial del acumulador);
const r1 = arr.reduce((accu, el)=> accu + el, 0);
console.log(r1); // 15

const getMax = (a,b) => Math.max(a,b);
const r2 = arr.reduce(getMax, 0);
console.log(r2); // 5

const getMax = (a,b) => Math.max(a,b);
const r3 = arrNeg.reduce(getMax);
console.log(r3); // -1

const r4 = users.reduce((accu, el) => 
  `${accu === '' ? '' : `${accu}, `}${el.name}`, '' );
console.log(r4); // 
```

# 4. fetch API

Fecth API es una funcionalidad implementada en JavaScript, especificamente en el explorador (No corre en Node.js) qué permite obtener datos desde una url mediante los métodos HTTP.

Se necesitasn dos archivos: 
- index.html
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <script type="text/javascript" src="./index.js"></script>
  <title>Document</title>
</head>
<body>
  ...
</body>
</html>
```
- index.js
```js
const url = 'https://jsonplaceholder.typicode.com/users';

//  Así pedimos data de una API para poderla consumir =================
// fetch( url, objeto para configurar la petición. OPCIONAL);
fetch(url)
  // .then((response) => console.log(response))
  // .then((response) => response.text()) // response.text() en el mismo then, permite parciarla a String
  .then((response) => response.json()) // response.json() en el mismo then, permite parciarla y trabajarla
  .then( data => console.log(data)) 
```

```js

//  Así pedimos enviar datos =================
const url = 'https://jsonplaceholder.typicode.com/users';

fetch(url,{
  method: 'POST', // 'PATCH','PUT','GET','DELETE'
  headers: {
    'Content-Type': 'application/json', // Así le indicamos al servidor que enviaremos datos tipo JSON
    'Authorization': 'Acadebieradeaparecerun token deautorización' // Así indicamos que hemos iniciado sesión, API_Key
  },
  body: JSON.stringify({ // Body contiene los datos que queremos enviarle al servidor. Debemos usar JSON.stringify()
    name: "Jorge",
    website: "jorgejogrewebsite"
  }) 
})
  .then((response) => response.json()) // response.json() en el mismo then, permite parciarla y trabajarla
  .then( data => console.log(data)) 
```

```js

// Usando async y await ==================================
const url = 'https://jsonplaceholder.typicode.com/users';

const fn = async () => {
  const response = await fetch(url,{  // Resplasa: .then((response) => response.json())
    method: 'POST', 
    headers: {
      'Content-Type': 'application/json', 
      'Authorization': 'Acadebieradeaparecerun token deautorización' 
    },
    body: JSON.stringify({ 
      name: "Jorge",
      website: "jorgejogrewebsite"
    }) 
  })
  const data = await response.json(); // Resplasa: .then( data => console.log(data)) 
  console.log(data);
}
```