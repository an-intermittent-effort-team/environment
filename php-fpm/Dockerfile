ARG PHP_VERSION
FROM php:${PHP_VERSION}
#RUN apt-get update \
#    && apt-get php-devel php-pear httpd-devel \
#    && pecl install yaf \
#    #&& pecl install swoole \
#    && docker-php-ext-enable yaf

USER root
RUN curl -sS https://getcomposer.org/installer | php \
    && mv composer.phar /usr/local/bin/composer \
    && chmod -R 777 /usr/local/bin/composer
