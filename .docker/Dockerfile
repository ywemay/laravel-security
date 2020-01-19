FROM php:7.4.1-apache

MAINTAINER Cibuc Dorian

COPY . /srv/app
COPY .docker/vhost.conf /etc/apache2/sites-available/000-default.conf

RUN chown -R www-data:www-data /srv/app \
    && a2enmod rewrite

RUN pecl install -o redis \
    && docker-php-ext-enable redis
    # && apt-get install -y libmemcached-dev zlib1g-dev \
    # && pecl install memcached-3.0.4 \
    # && docker-php-ext-enable memcached
