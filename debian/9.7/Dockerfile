FROM debian:9.7
LABEL maintainer "xiz - orz@xiz.im"

RUN echo deb http://mirrors.zju.edu.cn/debian jessie main >> /etc/apt/sources.list \
    && echo deb http://security.debian.org/debian-security jessie/updates main >> /etc/apt/sources.list \
    && echo deb http://mirrors.zju.edu.cn/debian stretch main >> /etc/apt/sources.list \
    && apt-get update \
    && apt-get install -y cmake g++ pkg-config git vim-common libwebsockets-dev libjson-c-dev libssl-dev \
    && git clone --depth=1 https://github.com/tsl0922/ttyd.git /tmp/ttyd \
    && cd /tmp/ttyd && mkdir build && cd build \
    && cmake -DCMAKE_BUILD_TYPE=RELEASE .. \
    && make \
    && make install \
    && apt-get autoremove -y \
    && rm -rf /var/lib/apt/lists/* \
    && rm -rf /tmp/ttyd \
EXPOSE 7681

ENTRYPOINT ["ttyd"]

CMD ["bash"]
