FROM php:8.0-fpm
COPY ./php.ini /usr/local/etc/php/
RUN apt-get update &&\
  #PHP GD Multibyte String
  apt-get install -y zlib1g-dev libpng-dev libwebp-dev libjpeg62-turbo-dev libonig-dev &&\
  docker-php-ext-configure gd --with-jpeg --with-webp &&\
  docker-php-ext-install -j$(nproc) gd &&\
  #PHP PDO MySQL
  docker-php-ext-install pdo_mysql mysqli
