# Base image: https://hub.docker.com/_/golang/
FROM golang:latest

LABEL maintainer="ethitter"
LABEL version="1.0"

# Install golint
ENV GOPATH /go
ENV PATH ${GOPATH}/bin:$PATH
RUN go install golang.org/x/lint/golint@latest

# Install clang
RUN apt-get update && apt-get install -y --no-install-recommends \
    clang \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

# Set Clang as default CC
ENV set_clang /etc/profile.d/set-clang-cc.sh
SHELL ["/bin/bash", "-o", "pipefail", "-c"]
RUN echo "export CC=clang-7.0" | tee -a ${set_clang} && chmod a+x ${set_clang}
