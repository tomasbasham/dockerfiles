FROM alpine:3.4

LABEL com.tomasbasham.maintainer "Tomas Basham <me@tomasbasham.co.uk>" \
      com.tomasbasham.version "1.15-r0" \
      com.tomasbasham.description "Automake - GNU Project"

ENV AUTOMAKE_VERSION 1.15-r0

# Install autotools
RUN apk add --no-cache automake=${AUTOMAKE_VERSION} \
  && rm -rf /var/cache/apk/*

RUN mkdir -p /usr/src/app
WORKDIR /usr/src/app

ENTRYPOINT ["/usr/bin/automake"]
CMD ["--help"]
