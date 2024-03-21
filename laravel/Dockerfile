FROM php:7.4-fpm

WORKDIR /var/www/html

RUN apt-get update && \
    apt-get install -y \
    libzip-dev \
    zip \
    unzip \
    git \
    && docker-php-ext-install zip pdo_mysql

RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

COPY . .

CMD php artisan serve --host=0.0.0.0 --port=8000
