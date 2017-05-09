# Capacitación Hexacta - Containers

![Docker](http://i.imgur.com/l5jHUaV.png)

## Contents

* Nginx
* Flask for developers
* Microservices
* Wordpress

## Links

* [Docker for Windows](https://www.docker.com/docker-windows)
* [Docker for Mac](https://www.docker.com/docker-mac)
* [Docker for Ubuntu](https://www.docker.com/docker-ubuntu)
* [Documentation](https://docs.docker.com/)

## Docker Commands

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
$ docker export container > container.tar # export container
$ tar -c container.tar # docker import - container:version # import container
$ run --name webapp -p 8080:80 -d container:version /usr/bin/supervisord # run imported image
```

## Projects commands

### Ubuntu base

```
$ docker run -it --name ubuntu ubuntu:latest
$ docker start ubuntu
$ docker exec -it ubuntu /bin/bash
$ docker stop ubuntu
$ docker rm ubuntu
```

### Nginx

```
$ docker build -t static-nginx:0.1.0 .
$ docker run --name static-nginx-v1 -p 8080:80 static-nginx:0.1.0

$ docker build -t static-nginx:0.1.1 .
$ docker run --name static-nginx-v2 -p 8080:80 static-nginx:0.1.1

$ docker run --name static-nginx-v3 -p 8080:80 -v ./src:/usr/share/nginx/html static-nginx:0.1.1

```

### Wordpress

```
$ docker-compose -f docker-compose.yml up --build
$ docker images
$ docker compose up
```

### Docker

```
$ docker ps -a | grep -v COMMAND | awk '{ print $1 }' | xargs docker rm 
$ docker images | grep -v REPOSITORY | awk '{ print $3 }' | xargs docker image rm
```