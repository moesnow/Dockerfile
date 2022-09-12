## How to use this image

`docker build -t xray .`

`docker run --name=xray --volume=/path/to/config.json:/root/config.json --volume=/path/to/acme.sh:/acme.sh --restart=always --detach=true xray`

