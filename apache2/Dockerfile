FROM centos:latest
MAINTAINER bitelxux@gmail.com

# Tell debconf to run in non-interactive mode
ENV DEBIAN_FRONTEND noninteractive

RUN yum update -y
RUN yum install -y httpd

RUN mkdir /var/www/html/coderdojo
COPY index.html /var/www/html/coderdojo
COPY coderdojo.png /var/www/html/coderdojo

EXPOSE 80

# Entry point
COPY start_apache.sh /root/
CMD ["/root/start_apache.sh"]

