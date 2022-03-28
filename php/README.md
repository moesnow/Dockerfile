## How to use this image

`docker build -t php:7.4-fpm-alpine-v1 .`

`docker run --name=php --volume=/var/run/php:/var/run/php --volume=/root/wwwroot:/wwwroot --volume=/path/to/zz-docker.conf:/usr/local/etc/php-fpm.d/zz-docker.conf:ro --workdir=/var/www/html --restart=always --detach=true php:7.4-fpm-alpine-v1`

## Configuration

### zz-docker.conf
```zz-docker.conf
[global]
daemonize = no

[www]
listen = /var/run/php/php.sock
listen.mode = 0666
```
