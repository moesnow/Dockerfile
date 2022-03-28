FROM alpine

ENV FRP_VERSION 0.41.0

RUN apk add tzdata && ln -sf /usr/share/zoneinfo/Asia/Shanghai /etc/localtime \
    && cd /root && wget https://github.com/fatedier/frp/releases/download/v${FRP_VERSION}/frp_${FRP_VERSION}_linux_amd64.tar.gz \
    && tar -xf frp_${FRP_VERSION}_linux_amd64.tar.gz && rm frp_${FRP_VERSION}_linux_amd64.tar.gz \
    && cd frp_${FRP_VERSION}_linux_amd64 && cp frpc /bin/ && mkdir /etc/frp/ && cp frpc.ini /etc/frp/ \
    && rm -rf /root/frp_${FRP_VERSION}_linux_amd64 \
    && rm -rf /var/cache/apk/* \
    && rm -rf /tmp/*

CMD ["frpc", "-c", "/etc/frp/frpc.ini"]
