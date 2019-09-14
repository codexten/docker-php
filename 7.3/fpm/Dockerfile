FROM devilbox/php-fpm:7.3-work

# composer installation
RUN php -r "readfile('http://getcomposer.org/installer');" | php -- --install-dir=/usr/bin/ --filename=composer
VOLUME /root/.composer
RUN composer global require hirak/prestissimo

CMD tail -f /dev/null
