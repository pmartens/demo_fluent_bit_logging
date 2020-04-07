FROM php:7.2.13-fpm-alpine3.8

WORKDIR /app

COPY php.ini /usr/local/etc/php/conf.d/php.override.ini
COPY www.conf /usr/local/etc/php-fpm.d/www.conf

CMD ["php-fpm", "--nodaemonize"]