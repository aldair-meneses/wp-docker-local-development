FROM wordpress:php8.2-fpm-alpine

RUN apk add --no-cache --update linux-headers

RUN apk add autoconf \
    g++ \
    make \
    && pecl install xdebug \
    && docker-php-ext-enable xdebug

WORKDIR /var/www/html

EXPOSE 9000
