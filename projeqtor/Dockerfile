FROM php:8.3-apache

RUN apt-get update && apt-get install -y unzip zlib1g zlib1g-dev libpng-dev libzip-dev
RUN docker-php-ext-install pdo_mysql
RUN docker-php-ext-install gd
RUN docker-php-ext-install zip
ADD php.ini /usr/local/etc/php/php.ini
RUN cd /var/www/html && curl -o projeqtor.zip https://psychz.dl.sourceforge.net/project/projectorria/projeqtorV11.2.3.zip?viasf=1
RUN cd /var/www/html && unzip projeqtor.zip && mv projeqtor/* . && rm -f *.zip
RUN chown -R www-data:www-data /var/www/html



