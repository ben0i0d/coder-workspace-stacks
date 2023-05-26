FROM eoelab.org:1032/build-image-stacks/coder-workspace-stacks/coder:cs

LABEL maintainer="eoelab <eoelab@eoelab.org>"

USER root
RUN apt-get update && \
    apt-get install -y --no-install-recommends build-essential && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

USER coder
