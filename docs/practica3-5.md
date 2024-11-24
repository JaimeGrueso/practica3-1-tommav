# Práctica 3.5: Despliegue de una aplicación Flask (Python)

## Jaime Grueso Martin

### Indice
1. [Prerrequisitos](#id1)
2. [Procedimiento Completo Para el Despliegue](#id2)

<div id="id1"></div>

## Prerrequisitos
Para esta práctica se deben tener las siguientes herramientas instaladas en el sistema:
    - Nginx
    - Gunicorn
    - Pipenv

<div id="id2"></div>

## Procedimiento Completo Para el Despliegue

Como primer paso, se ha de instalr el gestor de paquetes de Python pip:
![Python3-pip](./assets/images4/screenshot.2.jpg)

Una vez instalado pip, se ha de instalar pipenv:
![Pipenv](./assets/images4/screenshot.3.jpg)

Se crea un directorio para la aplicación. Al crearla se apreciará que los permisos pertenecen a **root**. Para cambiarlos se ha de ejecutar el comando `sudo chown -R $USER:$USER /home/jaime/app`:
`drwxr-xr-x  2 root root 4096 nov 21 15:53 flask_jaime`

Para ser cambiados se ejecutará el siguiente comando:
![Dueño](./assets/images4/screenshot.4.jpg)

Y se le cambiarán los permisos para que al iniciar Nginx no haya problemas:
![Permisos](./assets/images4/screenshot.5.jpg)

Ahora, dentro del directorio creado con anterioridad se creará el archivo oculto `.env`
![Archivo](./assets/images4/screenshot.7.jpg)

En el archivo `.env` se añadirán las siguientes lineas:
![Archivo](./assets/images4/screenshot.6.jpg)

Se iniciará el entorno virtual y `Pipenv` cargará las dependencias del archivo `.env`:

![Entorno](./assets/images4/screenshot.8.jpg)

Como se aprecia en la utima línea de la captura, aparece el nombre de nuestro entorno virtual, lo
cual significa que se ha iniciado correctamente.

Hecho esto, se instalarán las dependencias para la aplicación:
![Dependencias](./assets/images4/screenshot.9.jpg)

Se crearán los archivos `app.py` y `wsgi.py` que contendrán los siguientes codigos:
![Archivos](./assets/images4/screenshot.10.jpg)
![Archivos](./assets/images4/screenshot.11.jpg)

Se probará la aplicación con el comando siguiente:
![Prueba](./assets/images4/screenshot.12.jpg)

Si todo ha ido bien, si se accede al enlace proporcionado se podrá ver la aplicación funcionando:
![Funcionamiento](./assets/images4/screenshot.13.jpg)

Se comprobará ahora que Gunicorn funciona correctamente:
![Gunicorn](./assets/images4/screenshot.14.jpg)

Se tomará nota del path desde donde se ejectuta Gunicorn, para ello se ejecutará el siiguinte comandodentro de nuestro entorno virtual:
![Path](./assets/images4/screenshot.15.jpg)

Se saldrá del entorno virtual con `deactivate`.

Se iniciará Nginx si no estaba iniciado de antemano y se comprobará que sigue funcionando perfectamente:
![Nginx](./assets/images4/screenshot.16.jpg)

Se creará un archivo de configuración para que systemd ejecute Gunicorn como otro servicio mas:
![Configuracion](./assets/images4/screenshot.17.jpg)

Ahora se habilitará el servicio y se comprobará que se ha iniciado correctamente:
![Servicio](./assets/images4/screenshot.18.jpg)

Ahora se modifiará el archivo de configuración de Nginx de la siguiente manera:
![Nginx](./assets/images4/screenshot.19.jpg)

Se creará el enlace simbólico para que Nginx pueda acceder a los archivos de la aplicación:
![Enlace](./assets/images4/screenshot.20.jpg)

Se comptobará que la configuración de Nginx es correcta:
![Configuracion](./assets/images4/screenshot.21.jpg)

Se editará el archivo `hosts` para que se pueda acceder a la aplicación desde el navegador:

![Hosts](./assets/images4/screenshot.23.jpg)

Se comprobará que la aplicación funciona correctamente en el navegador:
![Hosts](./assets/images4/screenshot.22.jpg)

Ahora se deberá repetir el proceso para un repositorio que se clonará de GitHub:
![Repositorio](./assets/images4/screenshot.24.jpg)

Se creará el archivo `.env` con las variables de entorno necesarias:
![Repositorio](./assets/images4/screenshot.25.jpg)

Se cambiarán los permisos del directorio y los propietarios:
![Repositorio](./assets/images4/screenshot.26.jpg)

Se iniciliazará el entorno virtual:
![Repositorio](./assets/images4/screenshot.27.jpg)

Y se probará la aplicación:
![Repositorio](./assets/images4/screenshot.29.jpg)

Se comprobará que funciona correctamente:
![Repositorio](./assets/images4/screenshot.28.jpg)

Se comprobará que Gunicorn funciona correctamente:
![Repositorio](./assets/images4/screenshot.30.jpg)

Y se obtendrá el path de Gunicorn:
![Repositorio](./assets/images4/screenshot.35.jpg)

Se saldrá del entorno virtual y se creará el archivo de configuración para systemd:
![Repositorio](./assets/images4/screenshot.32.jpg)

Se configurará Nginx para que pueda acceder a la aplicación:
![Repositorio](./assets/images4/screenshot.33.jpg)

Se habilitará el servicio y se hará el enlace simbólico:
![Repositorio](./assets/images4/screenshot.34.jpg)

Una vez comprobada la configuración de Nginx, se editará el archivo `hosts` para poder acceder a la aplicación desde el navegador:
![Repositorio](./assets/images4/screenshot.38.jpg)

Se comprobará que la aplicación funciona correctamente:
![Repositorio](./assets/images4/screenshot.36.jpg)

Con esto se da por finalizada la práctica.






