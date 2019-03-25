FROM php:7.3.3-fpm

# RUN pecl install xdebug-2.7.0 \
#     && docker-php-ext-enable xdebug
    
RUN apt-get update && apt-get install -y \
        libzip-dev \
        zip \
        git \
        libpq-dev \
        libmcrypt-dev \
  && docker-php-ext-configure zip --with-libzip \
  && docker-php-ext-install zip \
  && docker-php-ext-install pdo_pgsql

RUN pecl install mcrypt-1.0.2 \
    && docker-php-ext-enable mcrypt

COPY --from=composer:latest /usr/bin/composer /usr/bin/composer