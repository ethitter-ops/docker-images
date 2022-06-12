FROM php:7.4-bullseye

LABEL maintainer="ethitter"
LABEL version="1.0"

RUN apt-get update \
    && apt-get -yqqf install \
      lsb-release \
      zip \
      unzip \
      rsync \
      subversion \
      git \
      libicu-dev \
      libpng-dev \
      libbz2-dev \
      default-libmysqlclient-dev \
      libzip-dev \
      libonig-dev \
      --fix-missing \
      --no-install-recommends \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*

RUN docker-php-ext-install \
      mbstring \
      mysqli \
      intl \
      gd \
      zip \
      bz2 \
    && pecl install xdebug \
    && php -m

SHELL ["/bin/bash", "-o", "pipefail", "-c"]
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer \
    && chmod +x /usr/local/bin/composer

ENV PATH=/root/.composer/vendor/bin:$HOME/.composer/vendor/bin:$PATH
