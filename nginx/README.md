![Hexacta](http://i.imgur.com/LwGwCTZ.jpg)

# Hexacta OpenTalk - DevOps: Containers

## Nginx

```
# version 1
$ docker build -t static-nginx:0.1.0 .
$ docker run --name static-nginx -p 8080:80 static-nginx:0.1.0
$ docker run --name static-nginx-dev -p 8080:80 -v ./src:/usr/share/nginx/html static-nginx:0.1.0
```
