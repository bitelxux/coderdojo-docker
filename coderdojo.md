# CoderDojo Malahide. Docker Presentation

Carlos Novo June 2017

##  Demo1: Apache on Ubuntu and DockerHub

  - [ ] docker run -it -p80:80 --name coderdojo ubuntu:16.04 bash
  - [ ] apt-get update
  - [ ] apt-get install apache2
  - [ ] service apache2 start
  - [ ] check browser
  - [ ] Ctrl+p+q
  - [ ] docker ps
  - [ ] create a repo in dockerhub
  - [ ] docker commit coderdojo
  - [ ] docker commit coderdojo bitelxux/coderdojo
  - [ ] docker rm -f coderdojo
    - [ ] apache is gone !
  - [ ] docker run -it -p80:80 --name coderdojo bitelxux/coderdojo bash
    - [ ] start apache
    - [ ] apache is back !
  - [ ] docker login
  - [ ] docker push bitelxux/coderdojo
  - [ ] docker rm -f coderdojo
    - [ ] apache is gone again :-(
  - [ ] docker rmi bitelxux/coderdojo
  - [ ] docker run -it -p80:80 --name coderdojo bitelxux/coderdojo bash
    - [ ] start apache
    - [ ] apache is back


## Demo2: Creating an image from scratch

  - [ ] docker build -t=coderdojo .
  - [ ] docker run -itd -p80:80 --name coderdojo bitelxux/coderdojo

## Some reference

This is not new ... Docker has only normalized/popularized the containers !!

https://en.wikipedia.org/wiki/Operating-system-level_virtualization

## FAQ

- Does it run on Windows ?

  Yes ! Windows Server 2016 and Windows 10 can run docker containers.
I haven't tested it though. I have a kind of alergy to Windows.
