FROM alpine as builder

WORKDIR /root

RUN apk --no-cache add go git make

RUN git clone https://github.com/m13253/dns-over-https.git \
    && cd dns-over-https && make

FROM alpine as prod

COPY --from=0 /root/dns-over-https/doh-client/doh-client /bin/
COPY --from=0 /root/dns-over-https/doh-client/doh-client.conf /etc/

CMD ["doh-client", "-conf", "/etc/doh-client.conf"]
