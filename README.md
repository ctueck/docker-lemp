docker-lemp
===========

A simple Dockerized (Linux-)Nginx-MariaDB-PHP stack

Tailor basic parameters in an `.env` file:

- `NGINX_TAG`: Tag of the Nginx image to use, default: `latest`
- `MARIADB_TAG`: Tag of the MariaDB image to use, default: `latest`
- `PHP_TAG`: Tag of the PHP image to start from, default: `8-fpm`
- `PHP_EXT`: PHP extensions to install with `docker-php-ext-install`
- `DB_PASSWORD`: Database password to use

Only the database password needs to be provided; database name and user name can be customised, but defaults are used by the MariaDB container and passed to the PHP container otherwise. These are available as `DB_NAME` and `DB_USER`. `DB_HOST` should not be changed, it points to the MariaDB container.

SQL dumps to initialise the database can be placed in `initdb.d/`, see [Initializing a fresh instance](https://hub.docker.com/_/mariadb/) for details. MariaDB data files will reside in a Docker-managed volume.

The web application should be placed in the directory `html/`.

By default, port `8080` is published on the Docker host. This can be customised in `WEB_PORT`.

