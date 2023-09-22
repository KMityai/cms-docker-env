FROM php:7.4-fpm-buster


RUN apt-get update && apt-get install -y \
	libzip-dev \
	libpng-dev \
	libjpeg-dev \
	libwebp-dev \
	libmcrypt-dev

RUN docker-php-ext-install -j$(nproc) mysqli pdo pdo_mysql zip
RUN docker-php-ext-configure gd --with-jpeg --with-webp && docker-php-ext-install -j$(nproc) gd
RUN pecl install mcrypt-1.0.6 && docker-php-ext-enable mcrypt
