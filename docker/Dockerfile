ARG PHP_VERSION=7.0
ARG COMPOSER_VERSION="2.2"

FROM composer/composer:${COMPOSER_VERSION} AS composer

FROM php:${PHP_VERSION}-cli AS php

ADD https://github.com/mlocati/docker-php-extension-installer/releases/latest/download/install-php-extensions /usr/local/bin/
RUN chmod +x /usr/local/bin/install-php-extensions

ARG PHP_EXTENSIONS="libsodium zip"
RUN install-php-extensions ${PHP_EXTENSIONS}

COPY --from=composer /usr/bin/composer /usr/bin/composer
