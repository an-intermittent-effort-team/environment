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
    && composer config -g repo.packagist composer https://mirrors.aliyun.com/composer/ \
    # 扩展
    && docker-php-ext-install -j$(nproc) bcmath calendar exif gettext sockets dba mysqli pcntl pdo_mysql shmop sysvmsg sysvsem sysvshm \
    # gd 安装
    && apt-get update && apt-get install -y --no-install-recommends  \
        libfreetype6-dev \
        libjpeg62-turbo-dev \
        libpng-dev \
        zip \
        libzip-dev \
        libbz2-dev \
        libpq-dev  \
        libxml2-dev \
        libtidy-dev \
        libxslt1-dev \
    && docker-php-ext-configure gd  --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/ \
    && docker-php-ext-install -j$(nproc) gd \
    && docker-php-ext-install -j$(nproc) soap wddx xmlrpc tidy xsl \
    && docker-php-ext-install -j$(nproc) pgsql pdo_pgsql \
    # bz2 安装
    && docker-php-ext-install -j$(nproc) bz2 \
    # redis 安装
    && pecl install redis-5.1.1 \
    && docker-php-ext-enable redis \
    # zip 安装
    && docker-php-ext-install -j$(nproc) zip

