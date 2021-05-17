FROM alpine

ENV XRAY_VERSION 1.4.2

RUN apk add tzdata wget && ln -sf /usr/share/zoneinfo/Asia/Shanghai /etc/localtime \
    && cd /root && wget https://github.com/XTLS/Xray-core/releases/download/v${XRAY_VERSION}/Xray-linux-64.zip \
    && unzip Xray-linux-64.zip && rm Xray-linux-64.zip \
    && wget -q https://raw.githubusercontent.com/ToutyRater/V2Ray-SiteDAT/master/geofiles/h2y.dat \
    && wget -qN https://github.com/Loyalsoldier/v2ray-rules-dat/releases/latest/download/geoip.dat \
    && wget -qN https://github.com/Loyalsoldier/v2ray-rules-dat/releases/latest/download/geosite.dat \
    && rm -rf /var/cache/apk/* \
    && rm -rf /tmp/*

CMD ["/root/xray", "-c", "/root/config.json"]
