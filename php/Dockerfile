FROM php:7.2.4-fpm

MAINTAINER "Majid Akbari <majidakbariiii@gmail.com>"

ARG WWW_DATA_USER_ID

RUN apt-get update && apt-get install -y \
    libmcrypt-dev \
    zip \
    unzip \
    zlib1g-dev \
    wget \
    vim \
    procps \
    iputils-ping \
    && docker-php-ext-install -j$(nproc) pdo pdo_mysql zip pcntl

RUN php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');" \
    && php composer-setup.php && php -r "unlink('composer-setup.php');" \
    && mv composer.phar /usr/local/bin/composer



RUN cd /var/www/html/ \
    && usermod -u ${WWW_DATA_USER_ID} www-data \
    && groupmod -g ${WWW_DATA_USER_ID} www-data \
    && chown -R www-data:www-data /var/www/
