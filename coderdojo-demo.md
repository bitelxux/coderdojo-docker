# CoderDojo Malahide. Docker Demo

Carlos Novo June 2017

## Before start

You want to install Docker on your machine ...

In Debian based distributions it is something like

```
sudo apt-get install docker.io
```

How to install it will vary depending on the OS you are running on your host.
A quick google search "how to install docker on <whatevertheosimrunningis" will lead you
to the answer.

##  Demo1: Apache on Ubuntu and push it to DockerHub

  - [ ] Run a container based on ubuntu

  ```
  sudo docker run -it -p80:80 --name coderdojo ubuntu:16.04 bash
  ```

  - [ ] update packages list

  ```
  apt-get update
  ```
  - [ ] Install apache

  ```
  apt-get install -y apache2
  ```

  - [ ] Start apache

  ```
  service apache2 start
  ```
  - [ ] check your browser at http://localhost
  - [ ] Exit the container without stopping it

  ```
  Ctrl+p+q
  ```

  - [ ] Check the container is still running

  ```
  sudo docker ps
  ```

  - [ ] If you don't have an account at hub.docker.com , it's time to create one ! 
  - [ ] Commit the changes locally

  ```
  sudo docker commit coderdojo
  ```

  - [ ] Prepare the container to be pushed to dockerHub

  ```
  sudo docker commit coderdojo <your dockerhub user>/coderdojo
  ```

  - [ ] Delete the container

  ```
  sudo docker rm -f coderdojo
  ```

  - [ ] apache is gone ( check your browser at http://localhost )!
  - [ ] Run again the container using the local image

  ```
  sudo docker run -it -p80:80 --name coderdojo <your dockerhub user>/coderdojo bash
  ```

  - [ ] start apache

  ```
  service apache2 start
  ```

  - [ ] apache is back ( check your browser at http://localhost )!
  - [ ] Login into DockerHub

  ```
  sudo docker login
  ```

  - [ ] Push the image to DockerHub

  ```
  sudo docker push <your dockerhub user>/coderdojo
  ```

  - [ ] Delete the container

  ```
  sudo docker rm -f coderdojo
  ```

  - [ ] apache is gone again :-( ( Check your browser )
  - [ ] Delete the local image

  ```
  sudo docker rmi <your dockerhub user>/coderdojo
  ```

  - [ ] Run again the container. This time the image will be pulled from DockerHub

  ```
  sudo docker run -it -p80:80 --name coderdojo <your dockerhub user>/coderdojo bash
  ```

  - [ ] start apache

  ```
  service apache2 start
  ```

  - [ ] apache is back ( check your browser at http://localhost )


## Demo2: Creating an image from scratch

  - [ ] cd to apache2 directory
  - [ ] Create the image based on Dockerfile file

  ```
  sudo docker build -t=coderdojo-image .
  ```

  - [ ] Run a container based on that image

  ```
  sudo docker run -itd -p80:80 --name coderdojo coderdojo-image
  ```

  - [ ] Check your browser http://localhost
  - [ ] Check your browser http://localhost/coderdojo

## Some reference

This is not new ... Docker has only normalized/popularized the containers !!

https://en.wikipedia.org/wiki/Operating-system-level_virtualization

## FAQ

- Does it run on Windows ?

  Yes ! Windows Server 2016 and Windows 10 can run docker containers.
I haven't tested it though. I have a kind of alergy to Windows.

## Slides

https://docs.google.com/presentation/d/1QsZYMy4-5tSuC-YsiBcEHXlUcGSy4GjyAI029_B0sto/edit?usp=sharing

## GIT

https://github.com/bitelxux/coderdojo-docker
