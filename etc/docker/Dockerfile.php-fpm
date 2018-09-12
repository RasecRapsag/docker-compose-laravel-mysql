FROM php:7.2-fpm

Maintainer Cesar Gaspar <rasec.rapsag@gmail.com>

RUN apt-get update && \
	apt-get install -y --no-install-recommends && \
	docker-php-ext-install pdo_mysql && \
	apt-get clean
