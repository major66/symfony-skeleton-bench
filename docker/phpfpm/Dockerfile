FROM php:7.2-fpm

RUN apt-get update && \
    apt-get install -y libpng-dev libjpeg-dev libpq-dev zip unzip sudo wget zlib1g-dev libicu-dev libzip-dev libzstd-dev g++ && \
    rm -rf /var/lib/apt/lists/*

RUN yes | pecl install igbinary redis grpc protobuf opencensus-alpha

RUN docker-php-ext-install intl && \
    docker-php-ext-install gd && \
    docker-php-ext-install mbstring && \
    docker-php-ext-install opcache && \
    docker-php-ext-install zip && \
    docker-php-ext-install calendar && \
    docker-php-ext-install sockets && \
    docker-php-ext-enable igbinary && \
    docker-php-ext-enable redis && \
    docker-php-ext-enable grpc && \
    docker-php-ext-enable protobuf && \
    docker-php-ext-enable opencensus

RUN rm -rf /var/www/html \
    && chmod 0777 /tmp/
