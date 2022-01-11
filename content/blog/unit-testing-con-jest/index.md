---
title: Unit Testing using Jest.js
date: "2021-01-4" 
description: "My notes about testing.."
---
<!-- date: año-mes-día -->

- [Jest.io](https://jestjs.io)
- [A Beginner’s Guide to Jest Testing](https://alialhaddad.medium.com/a-beginners-guide-to-jest-testing-858d10198032)
- [Jest testing: Top features and how to use them](https://blog.logrocket.com/testing-with-jest-from-zero-to-hero-85ce0e9cc953/)
- [DOM Testing React Applications with Jest](https://www.codementor.io/@pkodmad/dom-testing-react-application-jest-k4ll4f8sd)
- [How to Test React Components Using Jest](https://www.sitepoint.com/test-react-components-jest/)


## Goals
- Set up a testing environment with Jest
- Implement unit tests using Jest
- Configure Watch and Coverage in your project
- Create mocks for test suites

## What is Jest?

Jest is a JavaScript testing framework built by Facebook and primarily designed for React-based applications, but is also used with:
- Babel
- JavaScript
- Node
- Angular
- Vue
- NestJS
- GraphQL

## ¿What is a test?

A test is a prove of work about some code I want to check its predictable functionality.

## ¿What types of tests exist?
- **Functional testing**
    - **Unit Testing:** They are small tests on chunks of our code ensuring that they comply with what is desired.
- **Non Functional testing**

# 1. Jest.js Introduction 

## Preparing our work environment
1. ```git init``` to create our local repository
2. ```npm init``` to preparing our ork environment
3. ```npm install jest --save-dev``` to install Jest.js like a development dependencies
4. Inside **src** folder, we create a test folder call it **__test__** by dev community standards.
5. Inside **__test__** folder, the testing files have the next syntax name: **prove-name.test.js**
![folders](./screenshots/folders.png)

6. Next we have to go to **package.json** file and add this test script:
```js
  {
      "scripts": {
      "test": "jest"
    }
  }
```
We have two way to run our testing:
- ```npm run test```
- ```npm test```

To create a test, we use a function call **test()** that receives two parameters:
1. A string that describes the behavior to test
2. An anonymous function where we provide the behavior with a **expect function** and a **matcher function**
    - The [expect()](https://jestjs.io/docs/expect) function is used every time you want to test a value. You will rarely call expect by itself. Instead, you will use expect along with a "matcher" function to assert something about a value.
    - The [matcher()](https://jestjs.io/docs/using-matchers) function  let you test values in different ways. [ Find more Matchers](https://jestjs.io/docs/using-matchers).

Check the syntax in a simple example testing strings:
```js
let str = 'Hello sexy';

test("Input have the word: Hello", ()=>{
  expect(str).toMatch(/Hello/);
  expect(str).toMatch(/sexy/);
})
```
When the test is success we can see a image like this:
![successful test result](./screenshots/strUnitTesting.png)















# 2. Usando Jest.js con React.js
# 3. Deploy y CI con Travis