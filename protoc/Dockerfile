FROM ubuntu:zesty-20170915

LABEL com.tomasbasham.maintainer "Tomas Basham <me@tomasbasham.co.uk>" \
      com.tomasbasham.version "3.5.0" \
      com.tomasbasham.description "Protocol Buffers - Google's data interchange format"

ENV VERSION=3.5.0
ENV GRPC_VERSION=1.7.x

RUN apt-get update -q && apt-get install -y autoconf clang curl git libc++-dev libgflags-dev libtool make unzip \
  && git clone -b v${GRPC_VERSION} https://github.com/grpc/grpc \
  && cd grpc \
  && git submodule update --init \
  && make \
  && make install \
  && curl -o protoc-${VERSION}.zip -sSL https://github.com/google/protobuf/releases/download/v3.5.0/protoc-${VERSION}-linux-x86_64.zip \
  && unzip protoc-${VERSION}.zip -d /usr/local \
  && apt-get remove --purge -y autoconf clang curl git libc++-dev libgflags-dev libtool make unzip \
  && apt-get autoremove -y \
  && rm -rf /var/lib/apt/lists/* /grpc

RUN mkdir -p /usr/src/app
WORKDIR /usr/src/app

ENTRYPOINT ["/usr/local/bin/protoc"]
