#ARG PHP_VERSION
FROM php:7.3-fpm
RUN apt-get update \
    && apt-get php-devel php-pear httpd-devel \
    && pecl install yaf \
    #&& pecl install swoole \
    && docker-php-ext-enable yaf