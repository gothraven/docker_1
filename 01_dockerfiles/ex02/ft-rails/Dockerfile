# **************************************************************************** #
#                                                                              #
#                                                         :::      ::::::::    #
#    Dockerfile                                         :+:      :+:    :+:    #
#                                                     +:+ +:+         +:+      #
#    By: szaghban <marvin@42.fr>                    +#+  +:+       +#+         #
#                                                 +#+#+#+#+#+   +#+            #
#    Created: 2018/11/04 15:09:14 by szaghban          #+#    #+#              #
#    Updated: 2018/11/04 19:11:16 by szaghban         ###   ########.fr        #
#                                                                              #
# **************************************************************************** #

FROM ruby

MAINTAINER szaghban <szaghban@student.42.fr>

RUN apt-get update -y
RUN apt-get install -y build-essential libpq-dev nodejs sqlite3

ONBUILD COPY app /opt/app
ONBUILD WORKDIR /opt/app

ONBUILD EXPOSE 3000
ONBUILD RUN bundle install
ONBUILD RUN rake db:migrate
ONBUILD RUN rake db:seed

# docker build -t ft-rails:on-build .
