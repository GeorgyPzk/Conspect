# Docker command:

__Search__ some images:

`docker search <imagename>`

__Download__ image:

`docker pull <imagename>`

`docker pull georgypzk/lemp-stak-task5:v1`

__Show all__ images in VM:

`docker images`

__Show active__ containers:

`docker ps` `docker ps -a`

__Run__ image:

Inside (ctrl+c then ctrl+d to cancel):
 `docker run -it -p 80:8080 <imagename>`

Background:
 `docker run -d -p 80:8080 <imagename>` or

 `docker run -t -d  ubuntu:latest`

 `sudo docker run --name ubuntu1 -t -d -p 8081:80 27941809078c`

__Stop__ container:

`docker stop <imagename>`

`docker container prune` все остановленные контейнеры

__Delite__ container/image:

`docker rm <imagename>`

`docker rmi <imagename>`

__Restart__ container:

`docker restart my_container`

__Enter__ to container:

`docker exec -it <imagename> /bin/bash`

As __root__:

`docker exec -u 0 -it mycontainer bash`

__Create/Build__ image from __Dockerfile__:

`docker build -t mycontainer:v1 .`  `--no-cache` - without cache

__Create__ image from __container__:

`docker commit <idcontainer> <newname>:<version>`

__Docker compose__:

Background:
`docker-compose up --build -d`

`docker-compose -f ./docker-compose.app.yml up -d --build`

__Push__ image to __Docker hub__:

`docker login`

`docker tag <imageID> georgypzk/<imageName>:<version>`

`docker push georgypzk/<imageName>`

__SSH connection from container__:

`apt update && apt install  openssh-server sudo -y`

`chmod 600 Vm1_key.pem`

`ssh -i "Vm1_key.pem" -l azureuser 52.157.178.5 "docker ps -a"`


imagename == imageid 

[Some More](https://habr.com/ru/company/flant/blog/336654/)

# Docker compose

`docker compose -f ./docker-compose.app.yml up -d`