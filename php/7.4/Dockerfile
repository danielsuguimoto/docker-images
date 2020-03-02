FROM php:7.4-fpm-alpine

WORKDIR /app

RUN set -xe \
    && apt-get update \
    && apt-get install -y --no-install-recommends \
        libfreetype6-dev \
        libjpeg62-turbo-dev \
        libpng-dev \
        libzip-dev \
    && docker-php-ext-configure gd --with-freetype=/usr/include/ --with-jpeg=/usr/include/ \
    && docker-php-ext-install gd pdo_mysql zip exif pcntl opcache \
    && pecl install -o -f redis-5.0.2 \
    && docker-php-ext-enable redis \
    && curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer \
    && chmod a+x /usr/local/bin/composer \
    && rm -rf /tmp/pear \
    && rm -rf /var/lib/apt/lists/*