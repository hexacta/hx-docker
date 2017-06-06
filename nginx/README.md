![Hexacta](http://i.imgur.com/LwGwCTZ.jpg)

# Hexacta OpenTalk - DevOps: Containers

## Nginx

```
# version 1
$ docker build -t static-nginx:0.1.0 .
$ docker run --name static-nginx-v1 -p 8080:80 static-nginx:0.1.0

# version 2
$ docker build -t static-nginx:0.2.0 .
$ docker run --name static-nginx-v2 -p 8080:80 static-nginx:0.2.0

# version 3
$ docker build -t static-nginx:0.3.0 .
$ docker run --name static-nginx-v3 -p 8080:80 -v ./src:/usr/share/nginx/html static-nginx:0.3.0
```
