FROM debian:stretch

LABEL maintainer="ethitter"
LABEL version="1.0"

RUN echo "deb http://security.debian.org/ stretch/updates main" >> /etc/apt/sources.list

RUN apt-get update \
    && apt-get -y --no-install-recommends install \
        apt-transport-https \
        lsb-release \
        ca-certificates \
        curl \
        git \
        dh-make \
        build-essential \
        autoconf \
        autotools-dev \
        libpcre3 \
        libpcre3-dev \
        libz-dev \
        gnupg \
        libssl-dev \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*
