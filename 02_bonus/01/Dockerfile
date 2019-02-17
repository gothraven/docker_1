# **************************************************************************** #
#                                                                              #
#                                                         :::      ::::::::    #
#    Dockerfile                                         :+:      :+:    :+:    #
#                                                     +:+ +:+         +:+      #
#    By: szaghban <marvin@42.fr>                    +#+  +:+       +#+         #
#                                                 +#+#+#+#+#+   +#+            #
#    Created: 2018/11/04 15:20:21 by szaghban          #+#    #+#              #
#    Updated: 2018/11/04 21:22:42 by szaghban         ###   ########.fr        #
#                                                                              #
# **************************************************************************** #

# Ubuntu Container for nodejs prjects using yarn instead of npm

FROM ubuntu

MAINTAINER szaghban <szaghban@student.42.fr>

RUN apt-get update && apt-get upgrade -y && apt-get install -y nodejs npm git vim emacs
RUN npm install yarn --global && npm install npm --global

# docker build -t b01 .
# docker run --rm -ti b01
