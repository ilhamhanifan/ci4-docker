FROM php:8.0-fpm-alpine3.16

WORKDIR /var/www/html

RUN php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');"
RUN php composer-setup.php --install-dir=/usr/local/bin --filename=composer
RUN php -r "unlink('composer-setup.php');"

RUN apk add icu-dev

RUN docker-php-ext-install intl
RUN docker-php-ext-install mysqli

CMD composer install; chmod -R 777 writable ;php-fpm -F -R
