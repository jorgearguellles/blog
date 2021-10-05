---
title: Comandos de la Terminal
date: "2021-09-11" 
description: "Apuntos sobre los comandos de la Terminal"
---
<!-- date: año-mes-día -->
###  1. ¿Qué es la terminal?
Es una interfaz gráfica qué simula una linea de comandos, cuando hablamos de una linea de comandos hablamos de una _**shell**_
- **Terminal:** Es la ventana negra qué nos muestra el _**prompt**_ (Este aloja el shell)
- **Lineas de comandos (Shell):** Un programa que toma comandos, los interpreta y los pasa al sistema operativo para hacer algo.

### 2. ¿Qué es un comando?
Es un programa qué se puede ejecutar desde la terminal, puede recibir parámetros y opciones.


### 3. Comandos para moverse en la terminal
- **/:** Se le llama la raiz del sistema de archivos y desiende cómo un arbol
- **ls:** Listar todos los archivos contenidos en la carpeta en la que estoy
  - **ls -lS:** Listar archivos de acuerdo a su tamaño
  - **ls -lSh:** Listar archivos para ver su peso de una manera más legible
  - **ls -le:** Listar archivos en orden alfabéticos al revés
  - **ls -a:** Listar archivos ocultos
  - **ls _nombre_directorio_siguiente _:** Listar archivos al interior del directorio
  - **tree:** Permite ver todos los directorios del coputador en un diagrama de arbol
    - **tree -L _#_niveles_a_profundizar_:** Permite elegir hasta qué nivel muestra el diagrama de arbol con archivos
- **ctrl c:** Permite cerrar, finalizar o matar un proceso qué se este ejecutando en la terminal.
****
- **pwd:** Permite identificar la ruta en la que estamos en nuestro sistema
- **mkdir _nombre_directorio_:** Permite crear un directorio
  - **mkdir _nombre1_ _nombre2_ _nombre3_:** Permite crear varios directorios a la misma vez 
- **rmdir _nombre_directorio_:** Permite eliminar un directorio
****
- **cd:** Permite moverse entre las carpetas (change directory).
  - **cd _nombre_carpeta_** permite ingresar a una carpeta ("Adelante")
  - **cd ..** permite salir una carpeta ("Atras")
  - **cd** permite ir directamente a la raiz (/)
- **clear o ctrl l:** Permite limpiar la consola totalmente
  - **command l** permite limpiar la linea anterior
****
- **touch _nombre_archivo_:** Permite crear un archivo
  - **touch _nombre1_ _nombre2_  _nombre3_:** Permite crear varios archivos a la misma vez 
- **cp _archivo_a_copiar_ _nombre_de_la_copia_:** Permite copiar un archivo
- **mv _nombre_archivo_ _ruta_directorio_destino_:** Permite mover un archivo
  - **mv _nombre_archivo_ _nuevo_nombre_archivo_:** Permite renombrar un archivo
  - **mv _nombre_directorio_ _nuevo_nombre_directorio_:** Permite renombrar un directorio
- **file _nombre_archivo_:** Permite ver detalles del tipo de archivo
- **rm _nombre_archivo_:** Permite eliminar un archivo
  - **rm -i _nombre_archivo_:** Permite eliminar un archivo interactivamente
  - **rm -r _nombre_directorio_:** Permite eliminar un directorio y sus archivos contenidos de manera recrusiva.
  - **rm -rf _nombre_directorio_:** Permite eliminar de manera FORZADA un directorio y sus archivos contenidos de manera recrusiva.
  - **rm -ri _nombre_directorio_:** Permite eliminar de manera interactiva un directorio y sus archivos contenidos de manera recrusiva.
  ****
  - **head _nombre_archivo_:** Muestra la cabecera del archivo de texto. Las primeras 10 lineas por defecto.
  - **head _nombre_archivo_ -n  _#lineas_:** Muestra la cabecera del archivo de texto. Las primeras N lineas qué indiquemos.
  - **tail _nombre_archivo_ :** Muestra las últimas 10 lineas del archivo por defecto.
  - **tail _nombre_archivo_ -n  _#lineas_:** Muestra las últimas N lineas del archivo qué le indiquemos.
  - **less:** Tienes una interfaz gráfica e interactiva qué muestra todo el contenido del archivo de texto.
    - **/_termino_a_bucar_:** Permite buscar una palabra en el contenido del archivo
    - **q:** Permite salir de la interfaz gráfica.
  - **open _nombre_del_archivo_:** Permite abrir un archivo con us programa, por ejemplo Word, Excel, etc


