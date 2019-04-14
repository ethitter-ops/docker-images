FROM tetraweb/php:5.3

LABEL maintainer="ethitter"
LABEL version="1.0"

RUN apt-get update \
    && apt-get -yqqf install lsb-release zip unzip rsync subversion git mysql-client libicu-dev libpng-dev libbz2-dev libmysqlclient-dev libfreetype6-dev libjpeg-dev libxpm-dev --fix-missing --no-install-recommends \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*

RUN docker-php-ext-install mbstring mysqli intl gd zip bz2

SHELL ["/bin/bash", "-o", "pipefail", "-c"]
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer
RUN chmod +x /usr/local/bin/composer

ENV PATH=/root/.composer/vendor/bin:$HOME/.composer/vendor/bin:$PATH
