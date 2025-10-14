## Esquema para el ejercicio
![Imagen](esquema-4-ejercicio.PNG)

### Crear la red
docker network create net-wp

### Crear el contenedor mysql a partir de la imagen mysql:8, configurar las variables de entorno necesarias

docker run -d --name mysq-wp --network net-wp -e MYSQL_ROOT_PASSWORD=admin123 -e MYSQL_DATABASE=wordpressdb -e MYSQL_USER=wpuser -e MYSQL_PASSWORD=wppass mysql:8

### Crear el contenedor wordpress a partir de la imagen: wordpress, configurar las variables de entorno necesarias

docker run -d --name wordpress --network net-wp -p 9300:80 -e WORDPRESS_DB_HOST=mysql-wp:330 -e WORDPRESS_DB_USER=wpuser -e WORDPRESS_DB_PASSWORD=wppass -e WORDPRESS_DB_NAME=wordpressdb wordpress:latest

De acuerdo con el trabajo realizado, en el esquema del ejercicio el puerto a es 9300

Ingresar desde el navegador al wordpress y finalizar la configuración de instalación.

<img width="1919" height="1032" alt="image" src="https://github.com/user-attachments/assets/f120ad11-72dc-4774-b203-542b60b7d9d4" />


Desde el panel de admin: cambiar el tema y crear una nueva publicación.
Ingresar a: http://localhost:9300/ 
recordar que a es el puerto que usó para el mapeo con wordpress

<img width="1919" height="1035" alt="image" src="https://github.com/user-attachments/assets/4a1f2021-9999-4501-85d3-9e07d2e837d0" />


### Eliminar el contenedor wordpress

docker rm wordpress

### Crear nuevamente el contenedor wordpress
Ingresar a: http://localhost:9300/ 
recordar que a es el puerto que usó para el mapeo con wordpress

### ¿Qué ha sucedido, qué puede observar?
la pantalla se queda en blanco y no hay ningun cambio no asoma nada

