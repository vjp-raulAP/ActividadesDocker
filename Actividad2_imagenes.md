# Ejercicio para entregar

## Servidor web

1. Arranca un contenedor que ejecute una instancia de la imagen `php:7.4-apache`, que se llame **web** y que sea accesible desde tu equipo en el puerto 8000.

2. Coloca en el directorio raíz del servicio web (`/var/www/html`) de dicho contenedor un fichero llamado `index.html` con el siguiente contenido:

    ```html
    <h1>HOLA SOY XXXXXXXXXXXXXXX</h1>
    ```

   Deberás sustituir **XXXXXXXXXXXXX** por tu nombre y tus apellidos.

3. Coloca en ese mismo directorio raíz un archivo llamado `index.php` con el siguiente contenido:

    ```php
    <?php echo phpinfo(); ?>
    ```

Para crear los ficheros tienes tres alternativas:

- Ejecutando `bash` de forma interactiva en el contenedor y creando los ficheros.
- Ejecutando un comando `echo` en el contenedor con `docker exec`.
- Usando `docker cp` como hemos visto en el ejercicio 5.

## Servidor de base de datos

1. Arranca un contenedor que se llame **bbdd** y que ejecute una instancia de la imagen `mariadb` para que sea accesible desde el puerto 3336.

2. Antes de arrancarlo, visita la página del contenedor en Docker Hub y establece las variables de entorno necesarias para que:

    - La contraseña de `root` sea **root**.
    - Se cree automáticamente una base de datos llamada **prueba** al arrancar.
    - Se cree el usuario **invitado** con la contraseña **invitado**.

## Entregables

Deberás entregar los siguientes pantallazos comprimidos en un **zip** o en un **documento PDF**:

1. Pantallazo que desde el navegador muestre el fichero `index.html`.
2. Pantallazo que desde el navegador muestre el fichero `index.php`.
3. Pantallazo donde se vea el tamaño del contenedor **web** después de crear los dos ficheros.
4. Pantallazo donde desde un cliente de base de datos (instalado en tu ordenador) se pueda observar que hemos podido conectarnos al servidor de base de datos con el usuario creado y que se ha creado la base de datos **prueba** (`show databases`). El acceso se debe realizar desde el ordenador que tienes instalado Docker, no desde dentro del contenedor (es decir, no usar `docker exec`).
5. Pantallazo donde se comprueba que no se puede borrar la imagen **mariadb** mientras el contenedor **bbdd** está creado.
