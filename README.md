![Hexacta](http://i.imgur.com/LwGwCTZ.jpg)

# Hexacta OpenTalk - DevOps: Containers

![Docker](http://i.imgur.com/l5jHUaV.png)

## Contenidos

* Website estático con Nginx
* Flask para developers
* Microservicios
* Wordpress con MariaDB

## Links

* [Docker para Windows](https://www.docker.com/docker-windows)
* [Docker para Mac](https://www.docker.com/docker-mac)
* [Docker para Ubuntu](https://www.docker.com/docker-ubuntu)
* [Documentación](https://docs.docker.com/)

## Comandos básicos

```
$ docker --version # Version
$ docker images # list images
$ docker image rm <name|id> # delete image
$ docker run <image> # run container from image
$ docker start <name|id> # start container
$ docker stop <name|id> # stop container
$ docker ps [-a include stopped containers] # list containers
$ docker rm <name|id> # delete container
$ docker run --name webapp01 -p 8080:80 <name|id> # forward ports local:docker
$ docker run --name webapp01 -p 8080:80 -d <name|id> # as daemon
$ docker build -t webapp01 . # build
$ docker exec -ti webapp01 /bin/bash # enter in interactive mode
```

### Exportar container

```
$ docker export container > container.tar # export container
$ tar -c container.tar # docker import - container:version # import container
$ run --name webapp -p 8080:80 -d container:version /usr/bin/supervisord # run imported image
```

### Docker buscar y eliminar containers e imágenes

```
$ docker ps -a | grep -v COMMAND | awk '{ print $1 }' | xargs docker rm
$ docker images | grep -v REPOSITORY | awk '{ print $3 }' | xargs docker image rm
```

### Probado Ubuntu

```
$ docker run -it --name ubuntu ubuntu:latest /bin/bash
$ docker start ubuntu
$ docker exec -it ubuntu /bin/bash
$ docker stop ubuntu
$ docker rm ubuntu
```
