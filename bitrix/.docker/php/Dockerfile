FROM php:8.2-fpm-alpine

RUN apk add --no-cache \
	$PHPIZE_DEPS \
	libxml2-dev \
	libzip-dev \
	libpng-dev \
	libjpeg-turbo-dev \
	libwebp-dev \
	libmcrypt-dev \
	freetype-dev

RUN docker-php-ext-install -j$(nproc) mysqli pdo pdo_mysql zip xmlwriter
RUN docker-php-ext-configure gd --with-jpeg --with-freetype && docker-php-ext-install -j$(nproc) gd
RUN pecl install mcrypt-1.0.6 && docker-php-ext-enable mcrypt
