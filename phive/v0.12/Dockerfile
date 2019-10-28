FROM php:7.3-stretch

RUN apt-get update && \
    apt-get install -y --no-install-recommends \
        dirmngr=2.1.18-8~deb9u4 \
        gnupg=2.1.18-8~deb9u4 \
    && rm -rf /var/lib/apt/lists/*

ARG PHIVE_VERSION

RUN export BASE_URL="https://github.com/phar-io/phive/releases/download/${PHIVE_VERSION}" && \
    curl --silent --location --output phive.phar "${BASE_URL}/phive-${PHIVE_VERSION}.phar" && \
    curl --silent --location --output phive.phar.asc "${BASE_URL}/phive-${PHIVE_VERSION}.phar.asc" && \
    gpg --verbose --keyserver pool.sks-keyservers.net --recv-keys 0x9D8A98B29B2D5D79 && \
    gpg --verbose --verify phive.phar.asc phive.phar && \
    chmod +x phive.phar && \
    mv phive.phar /usr/local/bin/phive

RUN useradd docker -d /home/docker -u 1000 && \
    mkdir -p /home/docker/opcache /home/docker/composer /app && \
    chown -R docker:docker /home/docker /app

USER 1000
WORKDIR /home/docker

ENTRYPOINT ["/usr/local/bin/phive"]
