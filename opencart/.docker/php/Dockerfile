FROM php:7.4-fpm-alpine

RUN apk add --no-cache $PHPIZE_DEPS libzip-dev libpng-dev libjpeg-turbo-dev libwebp-dev libmcrypt-dev

RUN docker-php-ext-install -j$(nproc) mysqli pdo pdo_mysql zip
RUN docker-php-ext-configure gd --with-jpeg && docker-php-ext-install -j$(nproc) gd
RUN pecl install mcrypt-1.0.6 && docker-php-ext-enable mcrypt
