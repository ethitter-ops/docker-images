FROM tetraweb/php:5.3
MAINTAINER ethitter

RUN apt-get update && apt-get -yqqf install lsb-release zip unzip subversion mysql-client libicu-dev libpng-dev libbz2-dev libmysqlclient-dev libfreetype6-dev libjpeg-dev libxpm-dev --fix-missing
RUN docker-php-ext-install mbstring mysqli intl gd zip bz2

RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer
RUN chmod +x /usr/local/bin/composer

ENV PATH=/root/.composer/vendor/bin:$HOME/.composer/vendor/bin:$PATH
