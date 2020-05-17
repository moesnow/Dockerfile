FROM alpine as builder

WORKDIR /root

RUN apk --no-cache add go git make

RUN git clone https://github.com/m13253/dns-over-https.git \
    && cd dns-over-https && make

FROM alpine as prod

COPY --from=0 /root/dns-over-https/doh-client/doh-server /bin/
COPY --from=0 /root/dns-over-https/doh-client/doh-server.conf /etc/

CMD ["doh-server", "-conf", "/etc/doh-server.conf"]
