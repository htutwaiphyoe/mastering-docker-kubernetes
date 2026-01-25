# Mastering Docker

## 1. What is docker?

Docker -> lightweight virtualization for isolated env called containers

Docker solves it works on my machine

Docker shared machine kernel

[Download](https://www.docker.com/products/docker-desktop/) -> Install Docker Engine

Docker Container -> env to run

Docker Image -> thing to run on env

Data is not shared between Docker Container

## 2. Docker CLI

Must know CLI command for Linux evn

Docker Engine -> Management of Docker Container & Image

docker run -it ubuntu -> tell docker engine to run ubuntu image -> auto create container for that image

docker ps -a -> List containers

docker images -> List images

docker version

docker info

-i -> keep interactive -> standard input open

-t -> connected with container terminal

image -> check local first, then download

docker pull image -> download from hub.docker.com

docker image inspect image

docker image rm image -> remove container first docker container rm container

docker image prune -> remove all unused images
