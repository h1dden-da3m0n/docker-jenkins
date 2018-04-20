# k3rnelpan1c/docker-jenkins

A simple repo for the Dockerfiles I use to keep my docker-jenkins images up to date.

**Docker Hub image link** [k3rnelpan1c/docker-jenkins](https://hub.docker.com/r/k3rnelpan1c/docker-jenkins/)

Feel free to give me a heads up should I have an error in one of them or could improve them, but i WON'T add more than docker to the jenkins base image as there are more than enough other images on the hub that do that ;-)

Thanks for passing by or having a look! You are awesome!

# Docker Hub Description

Description & Versions Used
---
This image takes the jenkins/jenkins image in the current lts version and installs the latest version of Docker-CE to it.

| Program     	|            Version            	|
|-------------	|:-----------------------------:	|
| Jenkins LTS 	|          **2.107.2**          	|
| Docker CE   	| **18.03.0-ce** *(or 17.12.1-r0)* 	|

**INFO:** The Alpine version uses Docker version 17.12.1 since the base `jenkins/jenkins:lts-alpine` image is based on `alpine:3.7` and the latest version of Docker is not compatible with Alpine 3.7 ([Alpine package reverence](https://pkgs.alpinelinux.org/packages?name=docker&branch=v3.7))

- - -

Run the image
---
~~~sh
$ docker run -d -p 8080:8080 --name jenkins k3rnelpan1c/docker-jenkins
~~~
(If you don't specify a tag (docker-image-name:tag) at the end it will use `latest` as default)

Run with Persistent Data
===
To run Jenkins with persistent data you have to use docker volumes or like the folders you want to persist the content of to folders on your host machine.

Here are some examples:
~~~sh
$ docker run -d -p 8080:8080 --name jenkins k3rnelpan1c/docker-jenkins
~~~

Run so Jenkins can run Pipelines and Jobs in a Container
===
~~~sh
$ docker run -d -p 8080:8080 --name jenkins -v "/var/run/docker.sock:/var/run/docker.sock" k3rnelpan1c/docker-jenkins
~~~

Here the volume part (`-v "/var/run/docker.sock:/var/run/docker.sock"`) is important since it allows the docker deamon inside the Jeninks-Container to comunicate with the docker deamon on your host machine.
