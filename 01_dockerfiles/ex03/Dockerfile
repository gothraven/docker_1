# **************************************************************************** #
#                                                                              #
#                                                         :::      ::::::::    #
#    Dockerfile                                         :+:      :+:    :+:    #
#                                                     +:+ +:+         +:+      #
#    By: szaghban <marvin@42.fr>                    +#+  +:+       +#+         #
#                                                 +#+#+#+#+#+   +#+            #
#    Created: 2018/11/04 15:11:59 by szaghban          #+#    #+#              #
#    Updated: 2018/11/04 21:44:01 by szaghban         ###   ########.fr        #
#                                                                              #
# **************************************************************************** #

FROM ubuntu:16.04

MAINTAINER szaghban <szaghban@student.42.fr>

RUN apt-get update && \
    apt-get upgrade -y && \
    apt-get install -y ca-certificates openssh-server wget postfix

RUN wget https://packages.gitlab.com/install/repositories/gitlab/gitlab-ce/script.deb.sh && \
	chmod 777 script.deb.sh && \
	./script.deb.sh && \
	apt-get install -y gitlab-ce

RUN apt update && apt install -y tzdata && \
  apt-get clean && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

RUN apt-get clean && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

EXPOSE 443 80 22

ENTRYPOINT (/opt/gitlab/embedded/bin/runsvdir-start &) && gitlab-ctl reconfigure

# Get more space in the VM before using the Dockerfile
# docker-machine create -d virtualbox --virtualbox-memory 2048 --virtualbox-cpu-count 2 default

# docker build -t ex03 .
# docker container run -it --privileged  \
#       --hostname gitlab.example.com \
#       --publish 443:443 \
#       --publish 80:80 \
#       --publish 2222:22 \
#       --name c2222 \
#       --restart always \
#       --env docker_engine_ip="192.168.99.101" \
#       ex03
