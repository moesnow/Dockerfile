FROM nginx:alpine
RUN mkdir /etc/nginx/cache \
    && ln -sf /usr/share/zoneinfo/Asia/Shanghai /etc/localtime
COPY proxy_params /etc/nginx
