FROM ubuntu:xenial-20171006

LABEL com.tomasbasham.maintainer "Tomas Basham <me@tomasbasham.co.uk>" \
      com.tomasbasham.version "4.0.2" \
      com.tomasbasham.description "Swift"

# Set environment variables for image
ENV SWIFT_SNAPSHOT swift-4.0.2-RELEASE
ENV SWIFT_SNAPSHOT_LOWERCASE swift-4.0.2-release
ENV UBUNTU_VERSION ubuntu16.04
ENV UBUNTU_VERSION_NO_DOTS ubuntu1604

RUN apt-get update -q && apt-get install -y curl libicu-dev libcurl4-openssl-dev \
  && gpg --keyserver ipv4.pool.sks-keyservers.net --recv-keys 7463A81A4B2EEA1B551FFBCFD441C977412B37AD \
  && gpg --keyserver ipv4.pool.sks-keyservers.net --recv-keys 1BE1E29A084CB305F397D62A9F597F4D21A56D5F \
  && gpg --keyserver ipv4.pool.sks-keyservers.net --recv-keys A3BAFD3556A59079C06894BD63BC1CFE91D306C6 \
  && gpg --keyserver ipv4.pool.sks-keyservers.net --recv-keys 5E4DF843FB065D7F7E24FBA2EF5430F071E1B235 \
  && curl -o ${SWIFT_SNAPSHOT}-${UBUNTU_VERSION}.tar.gz -sSL https://swift.org/builds/${SWIFT_SNAPSHOT_LOWERCASE}/${UBUNTU_VERSION_NO_DOTS}/${SWIFT_SNAPSHOT}/${SWIFT_SNAPSHOT}-${UBUNTU_VERSION}.tar.gz \
  && curl -o ${SWIFT_SNAPSHOT}-${UBUNTU_VERSION}.tar.gz.sig -sSL https://swift.org/builds/${SWIFT_SNAPSHOT_LOWERCASE}/${UBUNTU_VERSION_NO_DOTS}/${SWIFT_SNAPSHOT}/${SWIFT_SNAPSHOT}-${UBUNTU_VERSION}.tar.gz.sig \
  && gpg --verify ${SWIFT_SNAPSHOT}-${UBUNTU_VERSION}.tar.gz.sig \
  && tar -zxf ${SWIFT_SNAPSHOT}-${UBUNTU_VERSION}.tar.gz ${SWIFT_SNAPSHOT}-${UBUNTU_VERSION}/usr/lib/swift/linux --strip-components=1 \
  && find /usr/lib/swift/linux -type f ! -name '*.so' -delete \
  && chmod -R go+r /usr/lib/swift \
  && apt-get remove --purge -y  curl icu-devtools  \
  && rm -rf /etc/ssl /${SWIFT_SNAPSHOT}-${UBUNTU_VERSION}.tar.gz /${SWIFT_SNAPSHOT}-${UBUNTU_VERSION}.tar.gz.sig \
    /usr/include /usr/share/man /tmp/* /var/lib/apt/lists/* /root/.gnupg

RUN mkdir -p /usr/src/app
WORKDIR /usr/src/app
