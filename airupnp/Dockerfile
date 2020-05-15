FROM ubuntu

RUN apt update && apt install -y wget openssl tzdata \
    && ln -sf /usr/share/zoneinfo/Asia/Shanghai /etc/localtime \
    && cd /root && wget https://github.com/philippe44/AirConnect/raw/master/bin/airupnp-x86-64 \
    && chmod +x airupnp-x86-64 \
    && mv airupnp-x86-64 /bin \
    && apt-get remove -y wget \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*

CMD ["airupnp-x86-64", "-Z", "-r"]
