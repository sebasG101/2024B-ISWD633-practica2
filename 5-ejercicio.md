## Esquema para el ejercicio
![Imagen](img/esquema-ejercicio5.PNG)

### Crear la red
```
docker network create net-wp -d bridge
```

### Crear el contenedor mysql a partir de la imagen mysql:8, configurar las variables de entorno necesarias
```
docker run -d --name cont-mysql -e MYSQL_ROOT_PASSWORD=password -e MYSQL_DATABASE=wordpressdb --network net-wp mysql:8
```

### Crear el contenedor wordpress a partir de la imagen: wordpress, configurar las variables de entorno necesarias
```
docker run -d --name cont-wordpress -p 9300:80 --network net-wp wordpress
```

De acuerdo con el trabajo realizado, en la el esquema de ejercicio el puerto a es **9300**

Ingresar desde el navegador al wordpress y finalizar la configuración de instalación.
# COLOCAR UNA CAPTURA DE LA CONFIGURACIÓN

![Imagen5](img/5.PNG)


Desde el panel de admin: cambiar el tema y crear una nueva publicación.
Ingresar a: http://localhost:9300/ 
recordar que a es el puerto que usó para el mapeo con wordpress
# COLOCAR UNA CAPTURA DEL SITO EN DONDE SEA VISIBLE LA PUBLICACIÓN.
![Imagen5.1](img/5.1.PNG)
### Eliminar el contenedor wordpress
```
docker stop cont-wordpress

docker rm cont-wordpress
```

### Crear nuevamente el contenedor wordpress
![Imagen5.2](img/5.2.PNG)
Ingresar a: http://localhost:9300/ 
recordar que a es el puerto que usó para el mapeo con wordpress

![Imagen5.3](img/5.3.PNG)

### ¿Qué ha sucedido, qué puede observar?
Se perdió toda la configuración realizada en el anterior contenedor.





