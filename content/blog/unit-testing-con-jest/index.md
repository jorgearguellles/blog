---
title: Unit Testing usando Jest.js en React.js
date: "2021-01-4" 
description: "Apuntes :.."
---
<!-- date: año-mes-día -->

- [Jest.io](https://jestjs.io)
- [A Beginner’s Guide to Jest Testing](https://alialhaddad.medium.com/a-beginners-guide-to-jest-testing-858d10198032)
- [Jest testing: Top features and how to use them](https://blog.logrocket.com/testing-with-jest-from-zero-to-hero-85ce0e9cc953/)
- [DOM Testing React Applications with Jest](https://www.codementor.io/@pkodmad/dom-testing-react-application-jest-k4ll4f8sd)
- [How to Test React Components Using Jest](https://www.sitepoint.com/test-react-components-jest/)


## Objetivos
- Configurar un entorno de Testing con Jest
- Implementar pruebas unitarias usando Jest
- Configurar Watch y Coverage en tu proyecto
- Crear Mocks para suites de pruebas

## What is Jest?

Jest is a JavaScript testing framework built by Facebook and primarily designed for React-based applications, but is also used with Babel, JavaScript, Node, Angular, and Vue. It can be used to test NestJS and GraphQL, too. Let’s take a look at some of best features of Jest.

## ¿Qué es un test?

Un test es una prueba que se le aplica a fragmentos de códigos con la intención de validar que ese códgio tiene un comportamiento predecible, retorna lo que se espera que retorne.

## ¿Qué tipos de Test Existen?
- **Pruebas funcionales**
    - **Pruebas Unitarias:** Se prueban pequeñas partes de nuestro codigo asegurandonos así que cumplen con lo que se desea. (En una pagina web las pruebas se traducen a probar cada sección de la pagina y todas las interacciones en ellas).
- **Pruebas no funcionales**

# 1. Introducción a Jest.js
## Preparando el entorno de trabajo
1. ```git init``` para crear el repositorio local
2. ```npm init``` para preparar el entorno que necesitamos para trabajar
3. ```npm install jest --save-dev``` para instalar Jest.js como dependencia de desarollo
4. Al interior de la carpeta **src** creamos una carpeta donde crearemos los tests que se llama **__test__** por standar de la comunidad.
5. Al interiot de la carpeta **__test__** los archivos tienen expención: **nombre-prueba.test.js**
6. ir al archivo **package.json** y configurar el script de test: ```"test": "jest"```. Para ejecutar las pruebas desde la terminal podemos hacerlas de dos maneras que funcionan igual :
    - ```npm run test```
    - ```npm test```
![folders](./screenshots/folders.png)

En jest trabajamos con una función que se llama ```test()```que recibe dos parametros:
1. Un strign que describe el comportamiento a probar
2. Una función anónima donde vamos

Jest usa "Matchers" para poder probar valores de diferentes maneras.
- [Documentación de más Matchers](https://jestjs.io/docs/using-matchers)
### Probando Strings
```js

let text = "hola sexy"

test("String have to contain sexy word", () => {
  expect(text) // String que recibe para aplicarle la prueba
    .toMatch(/sexy/); // La prueba a reaizar: verifica si en el STR que entrante contiene la palabra sexy
})
```
Cuando la pruyeba pasa exitosamente:
![successful test result](./screenshots/strUnitTesting.png)


- Los más comunes son:
    - **toBe()** usa _Object.is_ para probar la igualdad exacta
    ```js
    test('two plus two is four', () => {
      expect(2 + 2).toBe(4);
    });
    ```
    - **toEqual()** recursivamente verifica cada campo de un Arreglo
    ```js
    test('object assignment', () => {
      const data = {one: 1};
      data['two'] = 2;
      expect(data).toEqual({one: 1, two: 2});
    });
    ```

### Implementando pruebas a promesas













# 2. Usando Jest.js con React.js
# 3. Deploy y CI con Travis