FROM php:5.6-stretch
MAINTAINER ethitter

RUN apt-get update && apt-get -yqqf install lsb-release zip unzip subversion mysql-client libicu-dev libpng-dev libbz2-dev default-libmysqlclient-dev --fix-missing
RUN docker-php-ext-install mbstring mysqli intl gd zip bz2

RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer
RUN chmod +x /usr/local/bin/composer

ENV PATH=$HOME/.composer/vendor/bin:$PATH
