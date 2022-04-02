ARG PHP_TAG
FROM php:$PHP_TAG

# install Debian packages
ARG APT_GET
RUN test -z "$APT_GET" || ( \
    apt-get update && \
    apt-get install -y $APT_GET ; \
    apt-get clean ; \
    rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/* )

# install required PHP extensions
ARG PHP_EXT
RUN test -z "$PHP_EXT" || docker-php-ext-install $PHP_EXT

