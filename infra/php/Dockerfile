FROM php:8.4-fpm

RUN apt update \
    && apt install -y zlib1g-dev g++ git libicu-dev zip libzip-dev zip libpq-dev \
    && docker-php-ext-install intl opcache pdo pdo_pgsql \
    && pecl install apcu \
    && docker-php-ext-enable apcu \
    && docker-php-ext-configure zip \
    && docker-php-ext-install zip

WORKDIR /var/www/symfony_docker

RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

RUN apt-get install --no-install-recommends -y curl \
    && curl -Lo /tmp/symfony https://github.com/symfony/cli/releases/latest/download/symfony_linux_amd64 \
    && chmod +x /tmp/symfony \
    && mv /tmp/symfony /usr/local/bin/symfony \
    && git config --global user.email "thomas.jallu@gmail.com" \
    && git config --global user.name "Thomas"

COPY . /var/www/symfony_docker