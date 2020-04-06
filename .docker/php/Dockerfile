
FROM php:7.4-fpm

LABEL maintainer="Mario Mendoza"

COPY .docker/php/php.ini /usr/local/etc/php/php.ini

RUN apt-get -yqq update \
    && apt-get -yqq upgrade \
    && apt-get -yq install --no-install-recommends unzip wget curl git libzip-dev libicu-dev libcurl4-openssl-dev libpng-dev gnupg apt-transport-https  build-essential libaio1 zlib1g-dev  libxml2-dev \
    && docker-php-ext-install mysqli pdo_mysql zip gd pcntl curl intl xmlrpc\
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/* \
    && docker-php-source delete

WORKDIR /var/www/html

RUN chown -R www-data:www-data /var/www/html
RUN mkdir /var/moodledata && chmod 0777 /var/moodledata
RUN chown -R www-data:www-data /var/moodledata

RUN useradd -d /var/www/html appuser
RUN  adduser appuser sudo
USER appuser
