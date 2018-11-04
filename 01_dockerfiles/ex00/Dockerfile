# **************************************************************************** #
#                                                                              #
#                                                         :::      ::::::::    #
#    Dockerfile                                         :+:      :+:    :+:    #
#                                                     +:+ +:+         +:+      #
#    By: szaghban <marvin@42.fr>                    +#+  +:+       +#+         #
#                                                 +#+#+#+#+#+   +#+            #
#    Created: 2018/11/04 14:59:02 by szaghban          #+#    #+#              #
#    Updated: 2018/11/04 15:05:49 by szaghban         ###   ########.fr        #
#                                                                              #
# **************************************************************************** #

From alpine

MAINTAINER szaghban <szaghban@student.42.fr>

RUN apk update && apk upgrade && apk add vim

ENTRYPOINT vim

# docker build -t ex00 .
# docker run --rm -ti ex00
