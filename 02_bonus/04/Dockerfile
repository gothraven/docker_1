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

# Ubuntu Container for Php projects with Apache server

FROM ubuntu:12.04

MAINTAINER szaghban <szaghban@student.42.fr>

EXPOSE 80

RUN apt-get update &&
RUN apt-get install -y apache2 php5 libapache2-mod-php5 php5-mysql php5-cli
RUN apt-get clean && rm -rf /var/lib/apt/lists/*

ENV APACHE_RUN_USER www-data
ENV APACHE_RUN_GROUP www-data
ENV APACHE_LOG_DIR /var/log/apache2

COPY test.php ~/

CMD ["/usr/sbin/apache2", "-D", "FOREGROUND"]

# docker build -t b04 .
# docker run --rm -ti b04
