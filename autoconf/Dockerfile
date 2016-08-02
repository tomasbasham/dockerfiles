FROM alpine:3.4

LABEL com.tomasbasham.maintainer "Tomas Basham <me@tomasbasham.co.uk>" \
      com.tomasbasham.version "2.69-r0" \
      com.tomasbasham.description "Autoconf - GNU Project"

ENV AUTOCONF_VERSION 2.69-r0

# Install autotools
RUN apk add --no-cache autoconf=${AUTOCONF_VERSION} \
  && rm -rf /var/cache/apk/*

RUN mkdir -p /usr/src/app
WORKDIR /usr/src/app

ENTRYPOINT ["/usr/bin/autoconf"]
CMD ["--help"]
