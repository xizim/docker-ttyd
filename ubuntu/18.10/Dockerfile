FROM ubuntu:18.10
LABEL maintainer "xiz - orz@xiz.im"

RUN sed -i 's/archive.ubuntu.com/mirrors.aliyun.com/g' /etc/apt/sources.list \
    && echo deb http://security.ubuntu.com/ubuntu trusty-security main >> /etc/apt/sources.list \
    && echo deb http://kr.archive.ubuntu.com/ubuntu xenial main universe >> /etc/apt/sources.list \
    && apt-get update \
    && apt-get install -y --no-install-recommends \
      ca-certificates \
      cmake \
      curl \
      g++ \
      git \
      libjson-c2 \
      libjson-c-dev \
      libssl1.0.0 \
      libssl-dev \
      libwebsockets7 \
      libwebsockets-dev \
      pkg-config \
      vim-common \
    && git clone --depth=1 https://github.com/tsl0922/ttyd.git /tmp/ttyd \
    && cd /tmp/ttyd && mkdir build && cd build \
    && cmake -DCMAKE_BUILD_TYPE=RELEASE .. \
    && make \
    && make install \
    && apt-get autoremove -y \
    && rm -rf /var/lib/apt/lists/* \
    && rm -rf /tmp/ttyd \
    && ldconfig
EXPOSE 7681

ENTRYPOINT ["ttyd"]

CMD ["bash"]
