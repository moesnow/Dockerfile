FROM alpine

ENV XRAY_VERSION 1.4.2

RUN apk add tzdata && ln -sf /usr/share/zoneinfo/Asia/Shanghai /etc/localtime \
    && cd /root && wget https://github.com/XTLS/Xray-core/releases/download/v${XRAY_VERSION}/Xray-linux-64.zip \
    && wget https://raw.githubusercontent.com/ToutyRater/V2Ray-SiteDAT/master/geofiles/h2y.dat \
    && wget -N https://github.com/Loyalsoldier/v2ray-rules-dat/releases/latest/download/geoip.dat \
    && wget -N https://github.com/Loyalsoldier/v2ray-rules-dat/releases/latest/download/geosite.dat \
    && unzip Xray-linux-64.zip && rm Xray-linux-64.zip \
    && rm -rf /var/cache/apk/* \
    && rm -rf /tmp/*

CMD ["/root/xray", "-c", "/root/config.json"]
