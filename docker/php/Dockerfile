FROM php:7.4.1-fpm

# COPY php.ini
COPY ./docker/php/php.ini /usr/local/etc/php/php.ini

# Composer install
COPY --from=composer:2.0 /usr/bin/composer /usr/bin/composer

# copy Node.js
COPY --from=node:16 /usr/local/bin /usr/local/bin
COPY --from=node:16 /usr/local/lib /usr/local/lib

# その他使いそうなやつ
RUN apt-get update
RUN apt-get -y install git zip unzip vim libfreetype6-dev libjpeg62-turbo-dev libpng-dev
RUN docker-php-ext-install pdo_mysql bcmath

# 上記でgdをインストールしてしまうと最小構成(png使用可)になってしまう
# jpeg、webpを使えるようにしておく
RUN apt-get install -y zlib1g-dev libpng-dev libjpeg62-turbo-dev libwebp-dev
RUN docker-php-ext-configure gd --with-jpeg --with-webp
RUN docker-php-ext-install -j$(nproc) gd

WORKDIR /var/www/html