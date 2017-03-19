FROM golang:1.7

ARG GLIDE_VERSION=v0.12.3 \
    ARCH=linux-amd64

RUN mkdir -p /tmp/glide && \
    cd /tmp/glide && \
    curl -SsL https://github.com/Masterminds/glide/releases/download/${GLIDE_VERSION}/glide-${GLIDE_VERSION}-${ARCH}.tar.gz | \
    tar -xvz && \
    install -d $GOPATH/bin; \
    install -m 755 ./${ARCH}/glide $GOPATH/bin && \
    rm -rf /tmp/glide
