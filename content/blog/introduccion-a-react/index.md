---
title: Introducción a React.js
date: "2021-11-17" 
description: "Conceptos báscios para trabajar con React.js"
---
<!-- date: año-mes-día -->

Contenido de este post:

1. create-react-app
2. 

## 1. Creando una aplicación usando: create-react-app

Para crear una nueva aplicación usando React.js podemos usar el paquete _create-react-app_ el cual creará una plantilla inicial. La sintaxis para ejecutar el paquete, es un comando conformada por las siguientes tres partes:
```bash
npx create-reat-app mi-app
```
- **npx:** Es un comando que viene incluido dentro de npm despues de las versiones 5.2 qué lo que hace es: 
    - Ir a a buscar el paquete **_create-reat-app_**
    - Descargarlo
    - Ejecutarlo 
    - Le pasar el argumento: **_nombre-de-la-app_**
Este comando es importante porque así nos aseguramos de trabajar con la última versión del paquete. 

Al ejecutar el comando se descarga todo el paquete y finalmente nos indica unos comando que podriamos utilizar.

![comandos despues de instalar create-react-app](./img/1.png)

- **npm start:** Permite comenzar con el servidor de desarollo.
- **npm run build:** Permite generar un paquete enfocado para su uso en producción. Mimificarlo para que pese menos.
- **npm test:** Permite correr todos los test que hayamos escrito en nuestra app de react
- **npm run eject:** Elimina la herramienta de npm run eject y toma todos los arhciovs de configucarión y los deja en el directorio de nuestra App. Esto se hace cuando uno tiene qué personalizar una app de reaact muy a detalle.


## 2 Analisando la estructura del proyecto

![Estructura de carpetas del proyecto](./img/2.png)

- **Directorios**
    - **node_modules:** Este directorio es gigante porque contiene todas las dependencia necesarias para que podamos ejecutar nuestra aplicación en react.js. 
    ![Estructura de carpetas del proyecto](./img/3.png)
    - **public:** Contiene todos los archivos qué van a ser públicos para los usuarios.
    ![Estructura de carpetas del proyecto](./img/4.png)
    - **src:** Toda aplicación construida con **_create-react-app_** necesita única y exclusivamente dos archivos para poder funciuonar:
        - src/index.html
        - public/index.js (El más importante)
        
    ![Estructura de carpetas del proyecto](./img/5.png)
    - **.gitignore:** Contiene todos los archivos que tnemos que ignorar y no subir al repositorio, como por ejemplo las variables de entorno, las API keys, y otras credenciales.
- **Archivos**
    - **package-log.js** Contiene las dependencia que nosotros hemos instalado par el proyecto, cada dependencia con su versión y url. De esta manera cuando despelguemos la app a producción nos aseguramos de que instale las dependencias en la url indicada con la versión indicada y pueda funcionar.
    - **package.js** Contiene el nombre del proyecto, las dependencias instaladas de desarollo y de proudcción, si el repositoro es privado o publico, los cripts que se ejecutaran, configuración para el Linter.

## 3. Introducción a JSX, como funciona en react?


