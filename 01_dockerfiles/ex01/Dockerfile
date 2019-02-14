# **************************************************************************** #
#                                                                              #
#                                                         :::      ::::::::    #
#    Dockerfile                                         :+:      :+:    :+:    #
#                                                     +:+ +:+         +:+      #
#    By: szaghban <marvin@42.fr>                    +#+  +:+       +#+         #
#                                                 +#+#+#+#+#+   +#+            #
#    Created: 2018/11/04 15:02:02 by szaghban          #+#    #+#              #
#    Updated: 2018/11/04 21:11:02 by szaghban         ###   ########.fr        #
#                                                                              #
# **************************************************************************** #

FROM debian:latest

MAINTAINER szaghban <szaghban@student.42.fr>

ENV VERSION=3.6.1
ENV TS3SERVER_LICENSE=accept

EXPOSE 9987/udp 10011 30033

RUN apt-get update && apt-get upgrade -y
RUN apt-get install wget bzip2 -y

RUN wget http://dl.4players.de/ts/releases/${VERSION}/teamspeak3-server_linux_amd64-${VERSION}.tar.bz2
RUN tar -jxvf *.bz2

ENTRYPOINT ["./teamspeak3-server_linux_amd64/ts3server_minimal_runscript.sh"]

# Make sure to have TS3 client version 3.2.3
# docker build -t ex01 .
# docker run -it --rm -p 9987:9987/udp -p 10011:10011 -p 30033:30033 ex01
