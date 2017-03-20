FROM tomasbasham/erlang:18.3.2

LABEL com.tomasbasham.maintainer "Tomas Basham <me@tomasbasham.co.uk>" \
      com.tomasbasham.version "edge" \
      com.tomasbasham.description "Elixir"

ENV VERSION edge

# Install elixir and phoenix
RUN echo "@edge http://dl-cdn.alpinelinux.org/alpine/edge/community" >> /etc/apk/repositories \
  && apk add --no-cache elixir@${VERSION} \
  && mix local.hex --force \
  && mix local.rebar --force \
  && mix hex.info \
  && rm -rf /var/cache/apk/*

ENTRYPOINT ["/usr/bin/iex"]
