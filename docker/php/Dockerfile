FROM php:5.6-fpm

# Update apt-get and install a few things
RUN apt-get update && apt-get install -y \
        libmcrypt-dev \
        libicu-dev \
        libcurl4-gnutls-dev \
        libpng-dev \
        libxml2-dev \
        libxslt-dev \
        libpq-dev \
        libmemcached-dev \
        curl \
        openssl

# Install known available & needed php extensions
RUN docker-php-ext-install \
        bcmath \
        curl \
        gd \
        intl \
        mbstring \
        mcrypt \
        hash \
        pdo_mysql \
        simplexml \
        soap \
        xml \
        xsl \
        zip \
        json \
        iconv



# Install xdebug
RUN pecl install xdebug

# Copy xdebug config
COPY ./config/xdebug.ini /usr/local/etc/php/conf.d/