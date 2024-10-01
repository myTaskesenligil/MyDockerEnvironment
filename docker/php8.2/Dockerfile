FROM php:8.2-fpm

RUN apt-get update -y

RUN apt-get install -y libzip-dev zip unzip git curl libxml2-dev libfreetype6-dev libpng-dev libjpeg-dev libjpeg62-turbo-dev libpq-dev nano

RUN docker-php-ext-configure intl && docker-php-ext-install intl
RUN docker-php-ext-configure gd --with-freetype --with-jpeg && docker-php-ext-install gd

RUN docker-php-ext-install zip mysqli bcmath ctype fileinfo pdo pdo_mysql pdo_pgsql

RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

RUN chown -R www-data:www-data /var/www/html
