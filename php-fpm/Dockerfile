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
    && chmod -R 777 /usr/local/bin/composer \
    # gd 安装
    && apt-get update && apt-get install -y --no-install-recommends  \
        libfreetype6-dev \
        libjpeg62-turbo-dev \
        libpng-dev \
    && docker-php-ext-configure gd  --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/ \
    && docker-php-ext-install -j$(nproc) gd \
    # bz2 安装
    && apt-get install -y --no-install-recommends libbz2-dev  \
    && docker-php-ext-install -j$(nproc) bz2 \
    # redis 安装
    && pecl install redis-5.1.1 \
    && docker-php-ext-enable redis \
    #
    && docker-php-ext-install pcntl \
    #
    && apt-get install -y --no-install-recommends libzip-dev \
    && docker-php-ext-install -j$(nproc) zip

