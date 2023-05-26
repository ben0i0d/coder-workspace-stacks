FROM eoelab.org:1032/build-image-stacks/coder-workspace-stacks/coder:base

LABEL maintainer="eoelab <eoelab@eoelab.org>"

USER root
RUN apt-get update && \
    apt-get install -y --no-install-recommends build-essential && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

USER coder

RUN curl -fsSL https://code-server.dev/install.sh | sh -s -- --method=standalone --prefix=/tmp/code-server --version 4.11.0 && \
    /tmp/code-server/bin/code-server --auth none --port 13337 >/tmp/code-server.log 2>&1 