# subindo uma aplicacao laravel como exemplo
FROM php:7.4-cli

WORKDIR /var/www

# install lib
RUN apt-get update && \
    apt-get install libzip-dev -y && \
    docker-php-ext-install zip

# install composer
RUN php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');" && \
    php composer-setup.php && \
    php -r "unlink('composer-setup.php');"

# create laravel project
RUN php composer.phar create-project --prefer-dist laravel/laravel:^8.0 laravel

ENTRYPOINT [ "php", "laravel/artisan", "serve" ]

CMD [ "--host=0.0.0.0" ]