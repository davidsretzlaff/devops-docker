FROM php:7.4-cli

WORKDIR /VAR/WWW

RUN apt-get update && \
apt-get install libzip-dev -y && \
docker-php-ext-install zip

RUN php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');" && \ 
php composer-setup.php && \ 
php -r "unlink('composer-setup.php');" 

RUN php composer.phar create-project laravel/laravel laravel

# comando fixo
ENTRYPOINT [ "php","laravel/artisan", "serve" ]

# comando dinamico
CMD [ "--host=0.0.0.0" ] 