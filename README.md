# Practica-NGINX
## Trabajo realizado por Javier García Santiago y Pablo López Cabezas.
### Parte de Javier García, haciendo la parte de Docker.

### 1. Instalación Docker:
Primeramente tenemos que comprobar que tenemos Docker Desktop instalado y eso lo podemos hacer mediante **docker --version**:

![dockerVersion](capturas/version_docker.png)

En mi caso si lo tengo, pero si no lo tuvieramos tendríamos que descargarlo, siguiendo los pasos de la página web de Docker.

### 2. Creación de la Estructura de Carpetas:
Una vez visto que tenemos docker, clonamos nuestro repositorio de github a nuestro equipo local y comenzamos a hacer la estructura que va a tener nuestro proyecto.

![clonar](capturas/clonar-repositorio.png)

Y dentro de el, en la carpeta **html** clonamos el repositorio que dejastes en la entrega: **git clone https://github.com/cloudacademy/static-website-example .** 
El cuál lo he organizado de la siguiente forma:

![estructura](capturas/crear-carpetas.png)

### 3. Configuración de servidor web NGINX con Docker
Creamos el archivo de configuración **nginx.conf** dentro de la carpeta **conf**, y lo rellenamos con la siguiente información (en mi caso he puesto javier.test):

![nginx-conf](capturas/nginx-conf.png)

Una vez editado creamos un contenedor docker que ejecute nginx con un **docker run** y comprobamos que lo ha montado con un **docker ps -a**:

![docker-run](capturas/docker-run.png)

Y para ver los logs del contenedor lo podemos hacer mediante un **docker logs -f nginx-javier**:

![docker-logs](capturas/logs.png)

Una vez hecho todo esto, comprobamos en nuestro Docker Desktop que está el contenedor:

![compro](capturas/comprobacion-docker.png)

### 4. Comprobación del funcionamiento:
Viendo que existe nuestro contenedor y que está funcionando correctamente y vemos que el servidor está funcionando bien accediendo a **http://localhost**, y comprobamos que nos salga lo siguiente:

![local](capturas/localhost.png)

Editamos el archivo de host, que en en Windows se encuentra en la siguiente ubicación **C:\Windows\System32\drivers\etc** y añadimos donde está **127.0.0.1** el nombre de nuestro servidor( en mi caso javier.test )

![hosts](capturas/hosts.png)

Ahora con poner en nuestro navegador en la url el nombre de nuestro servidor saldrá nuestra página

![test](capturas/javier-test.png)

Como también podemos acceder **nip.io** que es añadiendo en la url de nuestro servidor **.nip.io**

![nip](capturas/nip.png)

### 5. Gestión del contenedor

Para detener, reiniciar y eliminar el contenedor, tenemos que añadir la palabra correspondiente en esta sentencia: **docker stop/restart/rm nginx-javier**:

![stop](capturas/stop.png)

### 6. Docker-compose

Docker-compose nos permite una configuración mas robusta y fácil de reproducir, y para conseguirlo, en la carpeta de nuestro proyecto (javier.test), creamos el archivo **docker-compose.yml** y le introducimos el siguiente contenido:

![compose](capturas/compose.png)

Para ejecutarlo debemos de hacer un **up -d**:

![up-d](capturas/compose-up.png)

Para ver los logs hacemos un **docker-compose logs -f**:

![logs](capturas/compose-log.png)

Y para detenerlo ejecutamos un **docker-compose down**:

![down](capturas/compose-down.png)







