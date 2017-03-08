FROM golang:1.7-alpine

RUN apk update && apk --no-cache add  build-base \
  make pkgconf wget ca-certificates  \
  openssl openssl-dev git libssh2-dev
RUN mkdir -p /go/tmp && \
  pkg-config --cflags freexl || cd /go/tmp  && \
    wget -c "http://www.gaia-gis.it/gaia-sins/freexl-1.0.2.tar.gz" && \
    tar -xvzf freexl-*.tar.gz && \
    cd freexl-*/ && \
    ./configure --prefix=/usr && \
    make && \
    make install && \
    make clean && \
    cd /go ; \
  rm -rf /go/tmp /var/lib/apt/lists/* /tmp/* /var/tmp/*
RUN mkdir -p /go/tmp && pkg-config --cflags libcurl || \
    cd /go/tmp && \
    wget -c https://curl.haxx.se/download/curl-7.49.1.tar.gz && \
    tar -xvzf curl-*.tar.gz && \
    cd curl-*/ && \
    ./configure --prefix=/usr --with-libssh2 --with-ssl && \
    make && \
    make install && \
    make clean && \
    cd /go ; \
  rm -rf /go/tmp /var/lib/apt/lists/* /tmp/* /var/tmp/*

