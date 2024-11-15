# Practica 3.2: Despliegue de Aplicaciones con Node Express

### Jaime Grueso Martin

## Indice
1. [Introducción](#id1)
2. [Instalación de Node.js, Express y Test de la Primera Aplicación](#id2)
3. [Despliegue de una Nueva Aplicación](#id3)
4. [Cuestiones](#id4)

<div id="id1"></div>

## Introducción
En esta práctica se procederá a el despliegue de aplicaciones con Node Express. 

Primeramente, se parará el servicio de Tomcat para evitar problemas a la hora de desplegar la aplicación.

![Parar Tomcat](./assets/images2/screenshot.1.jpg)

<div id="id2"></div>

## Instalación de Node.js, Express y Test de la Primera Aplicación
Para instalar Node.js y NPM, se ejecutará el siguiente comando:

![Instalación de Node.js](./assets/images2/screenshot.2.jpg)

Para comprobar que se han instalado correctamente, se ejecutarán el siguiente comando:

![Comprobar versión Node.js](./assets/images2/screenshot.3.jpg)

![Comprobar versión NPM](./assets/images2/screenshot.4.jpg)

A continuación, se procederá a clonar un repositorio de GitHub con una aplicación de ejemplo. Para ello, se ejecutará el siguiente comando y después se accederá a la carpeta de la aplicación:

<div id="id3"></div>

## Despliegue de una Nueva Aplicación

![Clonar repositorio](./assets/images2/screenshot.5.jpg)

Dentro de la carpeta de la aplicación, se ejecutará el siguiente comando para instalar las dependencias de la aplicación:

![Instalar dependencias](./assets/images2/screenshot.6.jpg)

Como se aprecia hay un error en la instalación de las dependencias, `sh: 1: nodemon: not found`. Para solucionar este error, se ejecutará el siguiente comando:

![Solucionar error](./assets/images2/screenshot.31.jpg)

Una vez solucionado el error, se procederá a ejecutar la aplicación con el siguiente comando:

![Ejecutar aplicación](./assets/images2/screenshot.30.jpg)

Si se accede a la dirección `http://localhost:3000/`, se podrá ver la siguiente pantalla:

![Pantalla aplicación](./assets/images2/screenshot.8.jpg)

<div id="id4"></div>

## Cuestiones
**Cuando ejecutáis el comando npm run start, lo que estáis haciendo es ejecutar un script:**

**¿Donde podemos ver que script se está ejecutando?**

**¿Qué comando está ejecutando?**

Cuando se ejecuta `npm run start`, el comando que se ejecuta está definido en el archivo `package.json`, en la sección `scripts`. Simplemente se abre `package.json` y se comprueba qué comando está asociado a `start`.

