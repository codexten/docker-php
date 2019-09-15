FROM devilbox/php-fpm:7.1-prod
RUN apt-get update
RUN apt-get install -y git --no-install-recommends

RUN apt-get install -y \
        libzip-dev \
        zip \
  && docker-php-ext-configure zip --with-libzip \
  && docker-php-ext-install zip
  
# composer installation
RUN php -r "readfile('http://getcomposer.org/installer');" | php -- --install-dir=/usr/bin/ --filename=composer
VOLUME /root/.composer
RUN composer global require hirak/prestissimo

CMD tail -f /dev/null
