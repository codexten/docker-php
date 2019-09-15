FROM codexten/php-fpm:7.1

RUN usermod -u 1000 www-data
RUN  apt-get -yq update && \
     apt-get -yqq install ssh

CMD tail -f /dev/null
