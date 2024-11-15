# Práctica 3.4: Despliegue de una Aplicación React en Netlify (PaaS)

## Jaime Grueso Martin

### Indice
1. [Creación de Nuestra Aplicación](#id1)
2. [Aplicación para Netlify](#id2)
3. [Proceso de Despliegue en Netlify](#id3)
    1. [Despliegue Mediante CLI](#id31)
    2. [Despliegue Mediante Conexión con Github](#id32)

<div id="id1"></div>

## Creación de Nuestra Aplicación
Primeramente, se deberá loggear en la máquina anfitriona con SSH. Para ello, se ejecutará el siguiente comando:

![Loggear en la máquina anfitriona](./assets/images3/screenshot.1.jpg)

Tras esto, se procederá a crear una carpeta en el escritorio que tendrá tres archivos: `head.html`, `tail.html` y `aplicacion.js`. Para ello, se ejecutarán los siguientes comandos:

![Crear carpeta](./assets/images3/screenshot.2.jpg)

Dentro de la carpeta, se han creado los archivos mencionados anteriormente y habrá que añadir el siguiente código a cada uno de ellos:

![Crear archivos](./assets/images3/screenshot.3.jpg)

![Crear archivos](./assets/images3/screenshot.4.jpg)

![Crear archivos](./assets/images3/screenshot.5.jpg)

Hecho esto, se podrá ejecutar el comando `npm init` para inicializar el proyeto y nos pedirá una serie de datos que deberemos rellenar. Y se ejecutará el comando `node aplicacion.js` para ejecutar la aplicación. 

![Inicializar proyecto](./assets/images3/screenshot.7.jpg)

Si se sabre una pestaña del navegador y se accede a la dirección `http://localhost:8080/`, se podrá ver la siguiente pantalla:

![Pantalla aplicación](./assets/images3/screenshot.6.jpg)

<div id="id2"></div>

## Aplicación para Netlify

Para poder desplegar nuestra aplicación en Netlify, se deberá clonar el repositorio que se nos ha facilitado.

![Clonar repositorio](./assets/images3/screenshot.8.jpg)

<div id="id3"></div>

## Proceso de Despliegue en Netlify

Se desplegaraá la aplicación en Netlify mediante dos métodos: mediante CLI y mediante conexión con Github.

Para ello la primera tarea será el loggearse en la web de Netlify. Y se generará un token de acceso que se utilizará cuando se nos pida loggearnos desde la terminal.

<div id="id31"></div>

### Despliegue Mediante CLI

Una vez se haya hecho el registro, se deberá instalar el cliente de Netlify dentro de la carpeta de la aplicación y se loggeará en la cuenta de Netlify:

![Instalar cliente](./assets/images3/screenshot.9.jpg)

![Loggear en Netlify](./assets/images3/screenshot.10.jpg)

Ahora se podrá instalar npm en la aplicación y se podrá desplegar la aplicación en Netlify con los siguientes comandos:

![Instalar npm](./assets/images3/screenshot.11.jpg)

![Desplegar aplicación](./assets/images3/screenshot.12.jpg)

Aqui se nos harán algunas preguntas que se deben responder de la siguiente manera:
Se creará y configurará un nuevo sitio
El Team se dejará por defecto
Y se le pone el nombre que se quiera al sitio y el directorio de despliegue será `./build`.

![Comando deploy](./assets/images3/screenshot.14.jpg)

![Comando deploy](./assets/images3/screenshot.15.jpg)


Si se accede a la dirección que se nos facilita, se podrá ver la aplicación desplegada en Netlify:

![Pantalla aplicación](./assets/images3/screenshot.13.jpg)

<div id="id32"></div>

### Despliegue Mediante Conexión con Github

Para desplegar la aplicación mediante conexión con Github, lo primero que se deberá hacer es eliminar la web que hemos creado para evitar posibles conflictos.

![Eliminar web](./assets/images3/screenshot.17.jpg)

Después, se deberá borrar el directorio que se clonó anteriormente con el comando `rm -rf color-shades-generator`. 

Hecho esto, nos descargaremos el repositorio pero con el comando siguiente:

![Clonar repositorio](./assets/images3/screenshot.18.jpg)

Se creará una carpeta nueva con el nombre de la prática y se extraerá el contenido del repositorio en ella.

![Crear carpeta](./assets/images3/screenshot.19.jpg)

Y nos colocaremos en la carpeta de la práctica. Ahora se creará un repositorio en Github y se subirán los archivos de la práctica a él.

![Crear repositorio](./assets/images3/screenshot.20.jpg)

Desde la web de Netlify, se seleccionará la opción de conectar con Github y se seleccionará el repositorio que se ha creado anteriormente.

![Conectar con Github](./assets/images3/screenshot.21.jpg)

Se seleccionará el repositorio:

![Deploy site](./assets/images3/screenshot.22.jpg)

Se seleccionará la rama principal y se comprobará que le nombre de la web no esté en uso:

![Deploy site](./assets/images3/screenshot.23.jpg)

Y finalmente se desplegará la aplicación:

![Deploy site](./assets/images3/screenshot.24.jpg)

Si se accede a la dirección que se nos facilita, se podrá ver la aplicación desplegada en Netlify:

![Pantalla aplicación](./assets/images3/screenshot.25.jpg)

Ahora se deberá modificar el archivo `robots.txt` para indicar a que URLs del sitio se pueden acceder.

![Modificar robots.txt](./assets/images3/screenshot.26.jpg)

Se hará un commit y un push de los cambios y en la pantalla de Netlify se podrá ver que se ha desplegado la nueva versión de la aplicación a la hora que se hizo el commit.

![Commit y push](./assets/images3/screenshot.29.jpg)

![Despliegue](./assets/images3/screenshot.27.jpg)


Si se accede a https://jaimito-3-4.netlify.app/robots.txt, se podrá ver el archivo `robots.txt` modificado:

![Pantalla aplicación](./assets/images3/screenshot.28.jpg)

Con esto se habrá completado la práctica.

