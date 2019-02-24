FROM debian:stretch

LABEL maintainer="ethitter"
LABEL version="1.0"

RUN echo "deb http://security.debian.org/ stretch/updates main" >> /etc/apt/sources.list

RUN apt-get update \
    && apt-get -yqqf --no-install-recommends install \
        apt-transport-https \
        lsb-release \
        ca-certificates \
        curl \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*

RUN curl -ssL -o /etc/apt/trusted.gpg.d/php.gpg https://packages.sury.org/php/apt.gpg
RUN echo "deb https://packages.sury.org/php/ $(lsb_release -sc) main" > /etc/apt/sources.list.d/php.list

RUN apt-get update \
    && apt-get -y --no-install-recommends install \
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
