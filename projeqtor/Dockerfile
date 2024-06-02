FROM php:8.3-apache

RUN apt-get update && apt-get install -y unzip zlib1g zlib1g-dev libpng-dev libzip-dev
RUN docker-php-ext-install pdo_mysql
RUN docker-php-ext-install gd
RUN docker-php-ext-install zip
ADD php.ini /usr/local/etc/php/php.ini
RUN cd /var/www/html && curl https://downloads.sourceforge.net/project/projectorria/projeqtorV11.2.3.zip?ts=gAAAAABmXGr11Y8i07I0pQfy2f3jbOk7wZoiM8NqaOmR3ScX9eBDUuSbNG1mVKsPHlCZtlrStj1czE-jVPZfYqEgEtqQBF_SMA%3D%3D&r=https%3A%2F%2Fsourceforge.net%2Fprojects%2Fprojectorria%2Ffiles%2FprojeqtorV11.2.3.zip%2Fdownload
ADD projeqtorV11.2.3.zip /var/www/html
RUN cd /var/www/html && unzip projeqtorV11.2.3.zip && mv projeqtor/* . && rm -f *.zip
RUN chown -R www-data:www-data /var/www/html



