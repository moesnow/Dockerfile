FROM alpine

ENV V2RAY_VERSION 4.45.2

RUN apk add tzdata wget && ln -sf /usr/share/zoneinfo/Asia/Shanghai /etc/localtime \
    && cd /root && wget -q https://github.com/v2fly/v2ray-core/releases/download/v${V2RAY_VERSION}/v2ray-linux-64.zip \
    && unzip v2ray-linux-64.zip && rm v2ray-linux-64.zip \
    && chmod +x /root/v2ray \
    && wget -q https://github.com/Loyalsoldier/v2ray-rules-dat/releases/latest/download/geoip.dat -O geoip.dat \
    && wget -q https://github.com/Loyalsoldier/v2ray-rules-dat/releases/latest/download/geosite.dat -O geosite.dat \
    && rm -rf /var/cache/apk/* \
    && rm -rf /tmp/*

CMD ["/root/v2ray", "-c", "/root/config.json"]