---
title: Git & GitHub
date: "2021-09-10" 
description: "Apuntes sobre mi aprendizage de Git & Github"
---
<!-- date: año-mes-día -->

# ¿Qué es Git?

- Es un sistema que guarda los cambios realizados a un archivo de manera atómica.
- Se usa en el computador, por medio de la terminal de comandos.

# Comandos básicos de Git

## ¿Cómo crear un repositorio local?
Un repositorio local se crea al escribir el comando <code>git init</code> y dar *Enter* al interior de la carpeta donde se quiere crear.

<details>
<summary>Ejemplo visual</summary>
Creacción de un repositorio local en la carpeta/directorio llamado test:
<img src="./images/3.png" style="margin:1rem 0;">
Nota: Puedes verificar la existencia del repositorio local con el comando <code>ls -la</code> qué nos listara los archivos visibles y los ocultos. En los archivos ocultos se debera ver un archivo <code>.git</code>
</details>
<br>
<br>

## ¿Cómo saber si hay archivos añadidos, borrados o editados en el proyecto? - ¿Cómo saber en cuál rama se esta? - ¿Cómo saber a qué archivos se les ha hecho *commit* o se les está haciendo seguimiento(Tracking)?
Con el comando <code>git status</code> y dar *Enter* al interior del proyecto.

<details>
<summary>Ejemplo visual</summary>

<img src="./images/4.png">
</details>
<br>
<br>

## ¿Cómo añadir un archivo al escenario o *staging* para hacerle seguimiento(Traking)?
Con el comando <code>git add</code> y dar *Enter* al interior del proyecto.

<details>
<summary>Ejemplo visual</summary>

<img src="./images/5.png">
</details>

## ¿Cómo elimino un archivo del escenario o *staging*?
Con el comando <code>git rm --cached</code> y dar *Enter* al interior del proyecto.

<details open>
<summary>Ejemplo visual</summary>

<img src="./images/6.png">
</details>



