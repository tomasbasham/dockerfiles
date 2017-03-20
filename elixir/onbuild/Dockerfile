FROM tomasbasham/elixir:edge

LABEL com.tomasbasham.maintainer "Tomas Basham <me@tomasbasham.co.uk>" \
      com.tomasbasham.description "Elixir"

ONBUILD COPY mix.exs /usr/src/app
ONBUILD COPY mix.lock /usr/src/app

ONBUILD RUN mix deps.get

ENTRYPOINT ["/usr/bin/mix"]
