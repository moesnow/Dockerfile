FROM alpine

ENV V2RAY_VERSION 4.38.3

RUN apk add tzdata wget && ln -sf /usr/share/zoneinfo/Asia/Shanghai /etc/localtime \
    && cd /root && wget https://github.com/v2fly/v2ray-core/releases/download/v${V2RAY_VERSION}/v2ray-linux-64.zip \
    && wget https://raw.githubusercontent.com/ToutyRater/V2Ray-SiteDAT/master/geofiles/h2y.dat \
    && wget -N https://github.com/Loyalsoldier/v2ray-rules-dat/releases/latest/download/geoip.dat \
    && wget -N https://github.com/Loyalsoldier/v2ray-rules-dat/releases/latest/download/geosite.dat \
    && unzip v2ray-linux-64.zip && rm v2ray-linux-64.zip \
    && rm -rf /var/cache/apk/* \
    && rm -rf /tmp/*

CMD ["/root/v2ray", "-c", "/root/config.json"]
