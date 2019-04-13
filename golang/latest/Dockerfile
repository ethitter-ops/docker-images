# Base image: https://hub.docker.com/_/golang/
FROM golang:latest

LABEL maintainer="ethitter"
LABEL version="1.0"

# Install golint
ENV GOPATH /go
ENV PATH ${GOPATH}/bin:$PATH
RUN go get -u golang.org/x/lint/golint

# Add apt key for LLVM repository
SHELL ["/bin/bash", "-o", "pipefail", "-c"]
RUN wget -O - https://apt.llvm.org/llvm-snapshot.gpg.key | apt-key add -

# Add LLVM apt repository
SHELL ["/bin/bash", "-o", "pipefail", "-c"]
RUN echo "deb http://apt.llvm.org/stretch/ llvm-toolchain-stretch-5.0 main" | tee -a /etc/apt/sources.list

# Install clang from LLVM repository
RUN apt-get update && apt-get install -y --no-install-recommends \
    clang-5.0 \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

# Set Clang as default CC
ENV set_clang /etc/profile.d/set-clang-cc.sh
SHELL ["/bin/bash", "-o", "pipefail", "-c"]
RUN echo "export CC=clang-5.0" | tee -a ${set_clang} && chmod a+x ${set_clang}
