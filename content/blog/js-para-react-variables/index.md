---
title: JavaScipt para React.js - Parte 1
date: "2021-11-10" 
description: "Repaso sobre los conceptos fundamentales de JavaScript para trabajar con React.js: Variables"
---
<!-- date: año-mes-día -->

Contenido de este post:

- Variables en JS: Var, let y const
- Arrow functions
- Export e import
- Clases

# Variables

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

# Arrow functions

