FROM php:8.3-apache

WORKDIR /var/www/html

RUN apt-get update \
    && apt-get install -y libonig-dev libzip-dev unzip mariadb-client \
    && docker-php-ext-install mbstring zip bcmath pdo_mysql mysqli \
    && pecl install xdebug 

COPY --from=composer:2 /usr/bin/composer /usr/bin/composer
ENV COMPOSER_ALLOW_SUPERUSER 1

COPY ./src /var/www/html