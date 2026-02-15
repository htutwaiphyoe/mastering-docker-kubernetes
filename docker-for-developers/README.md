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

--name name -> give name

docker kill -> shut down

docker container rm container -> remove

image has entry point -> bash

## 3. Docker File

source code -> docker image -> dockerize

Dockerfile -> config file

From image -> base image

COPY source target

RUN command

WORKDIR path

docker build App .

each command us a layer and each layer is cached

CMD [command]

use lightweight base image

order layer

Port mapping between host machine and container

-p host-port:container-port

auto Port mapping

EXPOSE 8000-8009

-itd -P --rm

hub.docker.com -> github for docker

docker push to hub.docker.com

docker tag LOCAL_NAME REMOTE_NAME
docker push LOCAL_NAME

multi stage docker build

docker delete everything of last stage

user in docker image

RUN addgroup --system -gid Id Name

RUN adduser --system -uid Id Name

USER Name

EXPOSE 8000
ENV PORT=8000

## 4. Docker Networking

[Networking](https://docs.docker.com/engine/network/)

Docker Network Driver

docker network

default -> bridge

containers can talk each other

docker exec ContainerName ping Ip

Default vs User-Defined Bridge

docker network create Network

docker network ls

docker run -itd --network=milkyway --name=Name --rm Image

network -> container -> image

automatic dns between container in same network

container detach to network

docker network connect Network Container

docker network disconnect Network Container

docker network rm Network

Network mode

- bridge
- host
- overlay

host -> no isolation -> direct to host interface

overly -> connect 2 docker daemons

ipvlan -> ip address allocation

macvlan -> docker container as seprate physical machine

none -> no internet connection -> no outside

## 5. Docker Volumes

container remove -> data clear

different container -> data isolation

access host data from container -> mount volume to container -> link to actual data -> reflect changes -> container remove -> still in host

-v HostFilePath:ContainerFilePath

read & write access by multiple docker container

\ for multiple line command

custom volume creation -> use by docker container

docker volume create Name

volume -> custom persistent data in docker

## 06. Docker Compose

docker-compose.yml

```yaml
name: Name

services:
  Name:
    build:
      context: .
      dockerfile: Dockerfile
    container_name: Name
    ports:
     - "HOST_PORT:CONTAINER_PORT"

  Name:
    image: Image
    depends_on:
      - ServiceName
    container_name: Name
    environment:
      ENV_NAME: ENV_VALUE
    ports:
     - "HOST_PORT:CONTAINER_PORT"
    networks:
      - Network
    volumes:
      - VolumeName:/FilePath

    -> docker run -it --name Name -e ENV_NAME=ENV_VALUE -p HOST_PORT:CONTAINER_PORT Image

networks:
  Name:
    driver: Network

volumes:
  Name:
```

docker compose up -d

docker compose down

auto create network by docker compose

build local image file in compose -> no need to publish on hub.docker.com

## 07. Docker Orchestration

container orchestration -> kubernetes and Docker Swarm

AWS CLI

ECR -> Elastic Container Registry -> Docker Hub

ECS -> Elastic Container Service -> Docker Orchestration

Cluster -> group of services

ECR -> ECS -> Containers -> Images

task definition -> same kernel

downscale services before delete

delete service, cluster, repository
