# VOLUMEN TIPO HOST
Un volumen host (o bind mount) es un tipo de volumen donde se monta un directorio o archivo específico del sistema de archivos del host en un contenedor.

```
docker run -d --name <nombre contenedor> -v <ruta carpeta host>:<ruta carpeta contenedor> <imagen> 
```

### Crear un volumen tipo host con la imagen nginx:alpine, para la ruta carpeta host: directorio en donde se encuentra la carpeta html en tu computador y para la ruta carpeta contenedor: /usr/share/nginx/html esta ruta se obtiene al revisar la documentación
![Volúmenes](imagenes/volumen-host.PNG)
```
docker run -d --name my_nginx -p 80:80 -v "D:\Joel\Universidad\Semestre 7\GitHubConstruccion\PracticasConstruccion\practica3\nginx\html":/usr/share/nginx/html nginx:alpine
```

### ¿Qué sucede al ingresar al servidor de nginx?
Al ingresar al servidor de nginx, es decir, al acceder a http://localhost:8080 en tu navegador después de ejecutar el comando anterior, el servidor de nginx servirá el contenido de la carpeta html que especificaste en tu computadora.

### ¿Qué pasa con el archivo index.html del contenedor?
si se pode un archivo index.html este mostrara en el localhost el contenido que esta dentro del index

### Ir a https://html5up.net/ y descargar un template gratuito, descomprirlo dentro de nginx/html
### ¿Qué sucede al ingresar al servidor de nginx?
El archivo index.html original del contenedor nginx será sobrescrito por el archivo index.html de la carpeta html de tu computadora.

### Eliminar el contenedor
```
docker rm -f my_nginx
```

### ¿Qué sucede al crear nuevamente el mismo contenedor con volumen de tipo host a los directorios definidos anteriormente?
El servidor nginx mostrará nuevamente el contenido de la carpeta html de tu computadora, que contiene el template HTML5 descargado.

### ¿Qué hace el comando pwd?
El comando pwd (print working directory) muestra la ruta absoluta del directorio de trabajo actual.

Si quieres incluir el comando pwd dentro de un comando de Docker, lo puedes hacer de diferentes maneras dependiendo del shell que estés utilizando.


### Volumen tipo host usando PWD y PowerShell
```
docker run -d --name <nombre contenedor> --publish published=<valorPuertoHost>,target=<valor> -v ${PWD}/<ruta relativa>:<ruta absoluta> <nombre imagen>:<tag> 
```

### Volumen tipo host usando PWD (Git Bash)

```
docker run -d --name <nombre contenedor> --publish published=<valorPuertoHost>,target=<valor> -v $(pwd -W)/html:/usr/share/nginx/html <nombre imagen>:<tag> 
```

### Volumen tipo host usando PWD (en Linux)

```
docker run -d --name <nombre contenedor> --publish published=<valorPuertoHost>,target=<valor> -v $(pwd)/html:/usr/share/nginx/html <nombre imagen>:<tag> 
```

