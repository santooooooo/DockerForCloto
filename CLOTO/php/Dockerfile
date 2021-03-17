FROM ubuntu:20.04
FROM php:7.4-apache

RUN apt-get -y update && apt-get -y upgrade
RUN apt-get -y install default-mysql-server default-mysql-client
RUN apt-get -y update
RUN apt-get -y install vim \
	git \
	sudo \
	zip \
	unzip
RUN git clone https://github.com/phpredis/phpredis.git /usr/src/php/ext/redis
RUN docker-php-ext-install pdo pdo_mysql redis

COPY --from=composer /usr/bin/composer /usr/bin/composer

EXPOSE 80
