FROM swift:4.0

LABEL com.tomasbasham.maintainer "Tomas Basham <me@tomasbasham.co.uk>" \
      com.tomasbasham.description "Swift"

RUN mkdir -p /usr/src/app
WORKDIR /usr/src/app

ONBUILD COPY Package.swift /usr/src/app
ONBUILD RUN swift package update
