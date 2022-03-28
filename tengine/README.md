## How to use this image

`docker build -t tengine .`

`docker run --name=nginx --volume=/path/to/conf.d:/etc/nginx/conf.d:ro --volume=/var/run/php:/var/run/php --volume=/path/to/nginx.conf:/etc/nginx/nginx.conf:ro --restart=always --detach=true tengine`

## Examples configuration

https://wiki.kotori.top/#/Linux/Nginx