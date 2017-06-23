# CoderDojo Malahide. Docker Demo

Carlos Novo June 2017

##  Demo1: Apache on Ubuntu and push it to DockerHub

  - [ ] Run a container based on ubuntu

  ```
  docker run -it -p80:80 --name coderdojo ubuntu:16.04 bash
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
  - [ ] check your browser
  - [ ] Exit the container without stopping it

  ```
  Ctrl+p+q
  ```

  - [ ] Check the container is still running

  ```
  docker ps
  ```

  - [ ] create a repo in DockerHub
  - [ ] Commit the changes locally

  ```
  docker commit coderdojo
  ```

  - [ ] Prepare the container to be pushed to dockerHub

  ```
  docker commit coderdojo bitelxux/coderdojo
  ```

  - [ ] Delete the container

  ```
  docker rm -f coderdojo
  ```

  - [ ] apache is gone ( check your browser )!
  - [ ] Run again the container using the local image

  ```
  docker run -it -p80:80 --name coderdojo bitelxux/coderdojo bash
  ```

  - [ ] start apache

  ```
  service apache2 start
  ```

  - [ ] apache is back ( check your browser )!
  - [ ] Login into DockerHub

  ```
  docker login
  ```

  - [ ] Push the image to DockerHub

  ```
  docker push bitelxux/coderdojo
  ```

  - [ ] Delete the container

  ```
  docker rm -f coderdojo
  ```

  - [ ] apache is gone again :-( ( Check your browser )
  - [ ] Delete the local image

  ```
  docker rmi bitelxux/coderdojo
  ```

  - [ ] Run again the container. This time the image will be pulled from DockerHub

  ```
  docker run -it -p80:80 --name coderdojo bitelxux/coderdojo bash
  ```

  - [ ] start apache

  ```
  service apache2 start
  ```
    - [ ] apache is back ( check your browser )


## Demo2: Creating an image from scratch

  - [ ] cd to apache2 directory
  - [ ] Create the image based on Dockerfile file

  ```
  docker build -t=coderdojo-image .
  ```

  - [ ] Run a container based on that image

  ```
  docker run -itd -p80:80 --name coderdojo coderdojo-image
  ```

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
