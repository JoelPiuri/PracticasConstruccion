## Esquema para el ejercicio
![Imagen](imagenes/esquema-ejercicio3.PNG)

### Crear red net-wp
```
docker network create net-wp
```


### Para que persista la información es necesario conocer en dónde mysql almacena la información.
# COMPLETAR LA SIGUIENTE ORACIÓN. REVISAR LA DOCUMENTACIÓN DE LA IMAGEN EN https://hub.docker.com/)
En el esquema del ejercicio la carpeta contenedor (a) es /var/lib/mysql. Ruta carpeta host: .../ejercicio3/db

### ¿Qué contiene la carpeta db del host?
La carpeta db del host contiene los archivos de base de datos de MySQL, tales como archivos de tabla, logs de transacciones, etc.


### Crear un contenedor con la imagen mysql:8  en la red net-wp, configurar las variables de entorno: MYSQL_ROOT_PASSWORD, MYSQL_DATABASE, MYSQL_USER y MYSQL_PASSWORD
```
docker run -d --name my_mysql --network net-wp -e MYSQL_ROOT_PASSWORD=my_root_password -e MYSQL_DATABASE=my_database -e MYSQL_USER=my_user -e MYSQL_PASSWORD=my_password -v "D:\Joel Universidad\Semestre 7\GitHubConstruccion\PracticasConstruccion\practica3\ejercicio3\db":/var/lib/mysql mysql:8
```

### ¿Qué observa en la carpeta db que se encontraba inicialmente vacía?
La carpeta db ahora contiene los archivos y directorios de base de datos MySQL, incluyendo los datos del sistema, las tablas, logs de transacciones, y archivos de configuración de la base de datos my_database.

### Para que persista la información es necesario conocer en dónde wordpress almacena la información.
En el esquema del ejercicio la carpeta contenedor (b) es /var/www/html Ruta carpeta host: .../ejercicio3/www

### Crear un contenedor con la imagen wordpress en la red net-wp, configurar las variables de entorno WORDPRESS_DB_HOST, 
```
docker run -d --name my_wordpress --network net-wp -p 80:80 -e WORDPRESS_DB_HOST=my_mysql:3306 -e WORDPRESS_DB_USER=my_user -e WORDPRESS_DB_PASSWORD=my_password -e WORDPRESS_DB_NAME=my_database -v "D:\Joel Universidad\Semestre 7\GitHubConstruccion\PracticasConstruccion\practica3\ejercicio3\www":/var/www/html wordpress
```

### Personalizar la apariencia de wordpress y agregar una entrada

### Eliminar el contenedor y crearlo nuevamente, ¿qué ha sucedido?
Cuando eliminas y creas nuevamente el contenedor de WordPress utilizando los mismos volúmenes, la personalización y las entradas que agregaste persisten. Esto sucede porque los datos se almacenan en las carpetas host (.../ejercicio3/www para WordPress y .../ejercicio3/db para MySQL) que no se borran al eliminar los contenedores.


