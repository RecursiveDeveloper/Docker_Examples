FROM ubuntu:22.04

# Stop dpkg-reconfigure tzdata from prompting for input
ENV DEBIAN_FRONTEND=noninteractive

RUN apt-get update && \
    apt-get -y install \
        apache2 \
        php \
        php-cli \
        php-fpm \
        php-json \
        php-common \ 
        php-zip \
        php-gd \
        php-mbstring \ 
        php-curl \
        php-xml \
        php-pear \
        php-bcmath 

WORKDIR /var/www/html

COPY apache.conf /etc/apache.conf

RUN echo "Hello World, $(whoami) user running php index file into apache server" > index.php

EXPOSE 80

CMD [ "apache2ctl", "-D", "FOREGROUND" ]
