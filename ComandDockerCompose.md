
# Comandos Docker y Docker Compose

## Descargar y crear contenedor con una imagen

1- Descargar la imagen `billingapp`:
```bash
docker pull sotobotero/udemy-devops:0.0.1
```

2- Crear el contenedor `billingapp`:
```bash
docker run -p 80:80 -p 8080:8080 --name billingapp sotobotero/udemy-devops:0.0.1
```

## Gestionar contenedores

- Listar los contenedores existentes:
```bash
docker ps -a
```

- Detener un contenedor:
```bash
docker stop nombreobjeto
```

- Ver los logs de un contenedor:
```bash
docker logs nombreobjeto
```

- Iniciar un contenedor detenido:
```bash
docker start nombreobjeto
```

- Forzar eliminar contenedot:
```bash
docker rm -f nombreobjeto
```

## Gestionar imágenes locales

- Listar las imágenes locales:
```bash
docker image ls
```

- Eliminar una imagen:
```bash
docker image rm nombreobjeto
```

- Forzar eliminar imagen:
```bash
docker rmi -f nombreobjeto
```

## Comandos Docker Compose

### Cuando el archivo no se llama docker-compose.yml

- Descargar las imágenes usando `docker-compose` :
```bash
docker-compose -f nombre_archivo.yml pull
```

- Iniciar los contenedores usando `docker-compose`:
```bash
docker-compose -f nombre_archivo.yml up -d
```

### Cuando el archivo si se llama docker-compose.yml

- Descargar las imágenes usando `docker-compose` :
```bash
docker-compose pull
```

- Iniciar los contenedores usando `docker-compose`:
```bash
docker-compose up -d
```

## Docker Compose para Adminer

- URL de la interfaz de Adminer:
   [http://localhost:9090/](http://localhost:9090/)

## Crear una nueva imagen y operaciones relacionadas

- Construir la imagen:
```bash
docker build -t billingapp:prod --no-cache --build-arg JAR_FILE=target/*.jar .
```

- Levantar el contenedor para probar:
```bash
docker run -p 80:80 -p 8080:8080 --name billingapp billingapp:prod
```

- Darle un nuevo tag a la imagen:
```bash
docker tag billingapp:prod sotobotero/udemy-devops:0.0.2
```

- Iniciar sesión en Docker Hub:
```bash
docker login
```

- Hacer un push de la imagen a Docker Hub:
```bash
docker push sotobotero/udemy-devops:0.0.2
```
