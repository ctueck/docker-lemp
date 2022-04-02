docker-lemp
===========

A simple Dockerized (Linux-)Nginx-MariaDB-PHP stack

Tailor basic parameters in an `.env` file:

- `DB_PASSWORD`: Database password to use - the only mandatory parameter
- `NGINX_TAG`: Tag of the Nginx image to use, default: `latest`
- `MARIADB_TAG`: Tag of the MariaDB image to use, default: `latest`
- `PHP_TAG`: Tag of the PHP image to start from, default: `8-fpm`
- `APT_GET`: packages to install with apt-get, default: none
- `PHP_EXT`: PHP extensions to install with `docker-php-ext-install`, default: none

Database name and user name can be customised, but defaults are used by the MariaDB container and passed to the PHP container otherwise. These are available as `DB_NAME` and `DB_USER`. `DB_HOST` should not be changed, it points to the MariaDB container.

SQL dumps to initialise the database can be placed in `initdb.d/`, see [Initializing a fresh instance](https://hub.docker.com/_/mariadb/) for details. MariaDB data files will reside in a Docker-managed volume.

The web application should be placed into the directory `html/` or in a directory or volume specified in `HTML_ROOT` (relative paths must start with `./`).

By default, port `8080` is published on the Docker host. This can be customised in `WEB_PORT`.

