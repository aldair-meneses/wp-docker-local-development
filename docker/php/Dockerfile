FROM wordpress:php8.3-fpm-alpine as base

RUN apk add --no-cache --update linux-headers

RUN apk add autoconf g++ make \
    && pecl install xdebug \
    && docker-php-ext-enable xdebug

env MYSQL_ROOT_PASSWORD=wordpress
env MYSQL_DATABASE=wordpress
env MYSQL_USER=wordpress
env MYSQL_PASSWORD=wordpress

FROM base as cli
RUN apk add --no-cache bash curl less mariadb-client

RUN curl -o /usr/local/bin/wp https://raw.githubusercontent.com/wp-cli/builds/gh-pages/phar/wp-cli.phar && \
    chmod +x /usr/local/bin/wp
