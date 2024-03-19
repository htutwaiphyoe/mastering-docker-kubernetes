# Docker and Kubernetes: The Complete Guide

Course by `Stephen Grider`

## 01. Why use Docker?

Docker makes easy to install and run software on any computers without worrying about setup and dependencies.

## 02. What is Docker?

Docker is the platform to create and run containers. It has a ecosystem consisting of docker image, docker compose, docker hub, docker client, docker server and docker machine.

docker cli => docker hub => docker image (single file containing all deps and configs required to run a program)

docker image => a single file stored on hard drive containing all deps and configs required to run a program

containers => instances of docker image => running program with its own isolated hardware resources

## 03. Docker for OS

Docker Client => CLI tool for running commands

Docker Server(Daemon) => tool for creating images and running containers

## 04. Docker Installation

[docker download](https://www.docker.com/get-started/)

docker version

## 05. Hello World Docker

docker run hello-world => docker client => docker server => image cache => docker hub => image cache => container

## 06. What is a container?

program => system call => kernel => hardware resources (CPU, Memory, Hard Disk)

name spacing => make portions of resources => isolate resources per process

control groups => limit the amount of resources for a process

container => running process + resources

docker image => filesystem snapshot + startup command
