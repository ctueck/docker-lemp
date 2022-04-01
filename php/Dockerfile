ARG PHP_TAG
FROM php:$PHP_TAG

# Install required extensions
ARG PHP_EXT
RUN test -z "$PHP_EXT" || docker-php-ext-install $PHP_EXT

