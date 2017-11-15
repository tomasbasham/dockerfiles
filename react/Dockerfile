FROM tomasbasham/node:5.11.1-alpine

LABEL com.tomasbasham.maintainer "Tomas Basham <me@tomasbasham.co.uk>" \
      com.tomasbasham.version "0.1.0-beta.3" \
      com.tomasbasham.description "React Command Line Interface"

ENV VERSION 0.1.0-beta.3
ENV PHANTOM_VERSION 2.1.14

# Install react and phantomjs§
RUN npm install -g \
  reactor-cli@${VERSION} \
  phantomjs-prebuilt@${PHANTOM_VERSION}

ENTRYPOINT ["/usr/bin/react”]
