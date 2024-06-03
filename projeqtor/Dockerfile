FROM php:8.3-apache

RUN apt-get update && apt-get install -y unzip zlib1g zlib1g-dev libpng-dev libzip-dev libfreetype-dev libjpeg-dev libc-client-dev libkrb5-dev
RUN docker-php-ext-install pdo_mysql
RUN docker-php-ext-configure gd --with-freetype --with-jpeg --enable-gd
RUN docker-php-ext-install gd
RUN docker-php-ext-install zip
RUN docker-php-ext-configure imap --with-kerberos --with-imap-ssl
RUN docker-php-ext-install imap
ADD php.ini /usr/local/etc/php/php.ini
ADD php.ini /etc/php/php.ini
RUN cd /var/www/html && curl -o projeqtor.zip https://psychz.dl.sourceforge.net/project/projectorria/projeqtorV11.2.3.zip?viasf=1
RUN cd /var/www/html && unzip projeqtor.zip && mv projeqtor/* . && rm -f *.zip
ADD initial-parameters.php /var/www/html/files/config/parameters.php
RUN chown -R www-data:www-data /var/www/html



