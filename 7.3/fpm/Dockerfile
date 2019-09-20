FROM devilbox/php-fpm:7.3-prod
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

RUN  apt-get -yq update && \
     apt-get -yqq install ssh

VOLUME /en
VOLUME /projects
VOLUME /var/www

ENV user www-data
RUN mkdir en
RUN chown -R ${user} /projects
RUN chown -R ${user} /en
RUN chown -R ${user} /var/www

USER ${user}

CMD php-fpm && tail -f /dev/null
