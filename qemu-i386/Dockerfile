FROM alpine:3.4

LABEL com.tomasbasham.maintainer "Tomas Basham <me@tomasbasham.co.uk>" \
      com.tomasbasham.version "2.5.1-r4" \
      com.tomasbasham.description "QEMU i386 guest support"

ENV VERSION 2.5.1-r4

# Install qemu
RUN apk add --no-cache qemu-system-i386=${VERSION} \
  && rm -rf /var/cache/apk/*

RUN mkdir -p /usr/src/app
WORKDIR /usr/src/app

ENTRYPOINT ["/usr/bin/qemu-system-i386"]
CMD ["--help"]
