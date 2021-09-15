FROM alpine

ENV XRAY_VERSION 1.4.3

RUN apk add tzdata wget && ln -sf /usr/share/zoneinfo/Asia/Shanghai /etc/localtime \
    && cd /root && wget -q https://github.com/XTLS/Xray-core/releases/download/v${XRAY_VERSION}/Xray-linux-64.zip \
    && unzip Xray-linux-64.zip && rm Xray-linux-64.zip \
    && chmod +x /root/xray \
    && wget -q https://github.com/Loyalsoldier/v2ray-rules-dat/releases/latest/download/geoip.dat -O geoip.dat \
    && wget -q https://github.com/Loyalsoldier/v2ray-rules-dat/releases/latest/download/geosite.dat -O geosite.dat \
    && rm -rf /var/cache/apk/* \
    && rm -rf /tmp/*

CMD ["/root/xray", "-c", "/root/config.json"]
