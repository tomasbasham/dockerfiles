FROM tomasbasham/node:6.11.0

LABEL com.tomasbasham.maintainer "Tomas Basham <me@tomasbasham.co.uk>" \
      com.tomasbasham.description "Node.js"

ONBUILD COPY package.json /usr/src/app
ONBUILD RUN npm install

ENTRYPOINT ["/usr/bin/npm"]
