# **************************************************************************** #
#                                                                              #
#                                                         :::      ::::::::    #
#    Dockerfile                                         :+:      :+:    :+:    #
#                                                     +:+ +:+         +:+      #
#    By: szaghban <marvin@42.fr>                    +#+  +:+       +#+         #
#                                                 +#+#+#+#+#+   +#+            #
#    Created: 2018/11/04 15:11:59 by szaghban          #+#    #+#              #
#    Updated: 2018/11/04 22:39:01 by szaghban         ###   ########.fr        #
#                                                                              #
# **************************************************************************** #

FROM ubuntu:16.04

MAINTAINER szaghban <szaghban@student.42.fr>

EXPOSE 443 80 22

RUN apt-get update
RUN apt-get upgrade -y
RUN apt-get install -y ca-certificates openssh-server wget postfix

RUN wget https://packages.gitlab.com/install/repositories/gitlab/gitlab-ce/script.deb.sh
RUN chmod 777 script.deb.sh
RUN ./script.deb.sh
RUN apt-get install -y gitlab-ce
RUN apt update && apt install -y tzdata
RUN apt-get clean && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

ENTRYPOINT (/opt/gitlab/embedded/bin/runsvdir-start &) && gitlab-ctl reconfigure && tail -f /dev/null

# Get more space in the VM before using the Dockerfile
# docker-machine create --driver virtualbox --virtualbox-memory 4096 --virtualbox-cpu-count 2 Char

# docker build -t ex03 .
# docker run -it -rm -p 8080:80 -p 8022:22 -p 8443:443 --privileged ex03
