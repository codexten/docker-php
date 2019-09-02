FROM php:7.3-cli

RUN set -eux; apt-get update

RUN docker-php-ext-install mbstring
RUN docker-php-ext-install exif
RUN docker-php-ext-install pdo pdo_mysql

# zip extension
RUN apt-get install -y libzip-dev zlib1g-dev
RUN docker-php-ext-install zip

#RUN docker-php-ext-install intl

# composer installation
RUN php -r "readfile('http://getcomposer.org/installer');" | php -- --install-dir=/usr/bin/ --filename=composer
RUN usermod -u 1000 www-data
VOLUME /root/.composer
RUN composer global require hirak/prestissimo