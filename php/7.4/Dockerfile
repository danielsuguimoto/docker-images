FROM php:7.4-fpm-alpine

WORKDIR /app

RUN apk --no-cache add autoconf su-exec bash git openssh-client icu shadow procps \
        freetype libpng libjpeg-turbo libzip-dev \
        jpegoptim optipng pngquant gifsicle libldap \
        freetype-dev libpng-dev libjpeg-turbo-dev \
        icu-dev libedit-dev libxml2-dev \
        openldap-dev oniguruma-dev \
    && docker-php-ext-configure gd --with-freetype=/usr/include/ --with-jpeg=/usr/include/ \
    && docker-php-ext-install gd pdo pdo_mysql zip exif pcntl opcache mbstring intl\
    && pecl install redis \
    && docker-php-ext-enable redis \
    && curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer \
    && chmod +x /usr/local/bin/composer