FROM tomasbasham/erlang:18.3.2

LABEL com.tomasbasham.maintainer "Tomas Basham <me@tomasbasham.co.uk>" \
      com.tomasbasham.description "Erlang"

ONBUILD COPY rebar.config /usr/src/app
ONBUILD RUN rebar3 compile

ENTRYPOINT ["/usr/bin/rebar3"]
