FROM alpine:3.11

ENV V2RAY_VERSION 4.23.1

RUN apk add tzdata && ln -sf /usr/share/zoneinfo/Asia/Shanghai /etc/localtime \
    && cd /root && wget https://github.com/v2ray/v2ray-core/releases/download/v${V2RAY_VERSION}/v2ray-linux-64.zip \
    && wget https://raw.githubusercontent.com/ToutyRater/V2Ray-SiteDAT/master/geofiles/h2y.dat \
    && unzip v2ray-linux-64.zip && rm v2ray-linux-64.zip \
    && rm -rf /var/cache/apk/* \
    && rm -rf /tmp/*

CMD ["/root/v2ray", "-c", "/root/config.json"]
