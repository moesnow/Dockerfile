FROM alpine

ENV SPEEDTEST_VERSION 1.2.0

RUN tempDir="$(mktemp -d)" && cd $tempDir \
    && wget https://install.speedtest.net/app/cli/ookla-speedtest-${SPEEDTEST_VERSION}-linux-x86_64.tgz \
    && tar xzvf ookla-speedtest-${SPEEDTEST_VERSION}-linux-x86_64.tgz \
    && mv speedtest /usr/local/bin/ \
    && mkdir -p /root/.config/ookla/ \
    && rm -rf $tempDir

COPY speedtest-cli.json /root/.config/ookla/

CMD ["speedtest"]
