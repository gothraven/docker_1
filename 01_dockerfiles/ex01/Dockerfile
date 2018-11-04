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

FROM debian

MAINTAINER szaghban <szaghban@student.42.fr>

ENV TS3SERVER_LICENSE accept

EXPOSE 9987/udp 10011 30033

RUN adduser --system teamspeak \
	&& apt-get update -y \
	&& apt-get install wget bzip2 -y \
	&& wget http://dl.4players.de/ts/releases/3.4.0/teamspeak3-server_linux_amd64-3.4.0.tar.bz2 \
	&& tar -xvf teamspeak3-server_linux_amd64-3.4.0.tar.bz2 \
	&& mv teamspeak3-server_linux_amd64 teamspeak3 \
	&& rm teamspeak3-server_linux_amd64-3.4.0.tar.bz2 \
	&& mv teamspeak3 /home/teamspeak

WORKDIR /home/teamspeak

ENTRYPOINT sh teamspeak3/ts3server_minimal_runscript.sh license_accepted=1

# docker build -t ex01 .
# docker run --rm -p 9987:9987/udp -p 10011:10011 -p 30033:30033 ex01
