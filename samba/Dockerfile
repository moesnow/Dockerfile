FROM alpine

RUN apk add tzdata samba && ln -sf /usr/share/zoneinfo/Asia/Shanghai /etc/localtime \
    && chmod 0777 /home \
    && rm -rf /var/cache/apk/* \
    && rm -rf /tmp/*

CMD ["smbd", "--foreground", "--no-process-group"]
