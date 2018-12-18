# common PHP for Docker

* extends [humilit/common](https://github.com/humilit/common)
* base of [humilit/php-apache](https://github.com/humilit/php-apache)

## integrated tools

## configuration

### Sessions

This image will store PHP sessions in `memcache`, given a `memcache` container is available in this stack.
Storing sessions in `memache` allows scaling of a php-application to any number of hosts, given they use the same `memcache`.

Use e.g. `memcached:1.5-alpine` from dockerhub with cmd param `-m 256` for 256 MB max size

## configuration
for all those settings try to keep them as small as possible 
and route paths that need more (e.g. a backend) to a separate container with higher limits
before increasing the limits for the whole application.

* **PHP_TIME_LIMIT** (default: `10`) time limit for the execution of a PHP script
* **PHP_MEMORY_LIMIT** (default: `64M`) maximum memory usage for a PHP script
* **PHP_POST_SIZE_LIMIT** (default: `8M`) maximum size of a POST request
* **PHP_UPLOAD_SIZE_LIMIT** (default: `8M`) maximum size of a file for a POST request
