FROM eoelab.org:1032/mirrored-sources/mirror-image-stacks/ubuntu:22.04

LABEL maintainer="eoelab <eoelab@eoelab.org>"


USER root
ENV DEBIAN_FRONTEND noninteractive
RUN sed -i 's@//.*archive.ubuntu.com@//mirrors.ustc.edu.cn@g' /etc/apt/sources.list && \
    sed -i 's/security.ubuntu.com/mirrors.ustc.edu.cn/g' /etc/apt/sources.list && \   
    apt-get update && \
    apt-get install -y --no-install-recommends bash ca-certificates git bash curl wget nano vim sudo && \
    wget http://eoelab.org:1024/index.php/s/XHeP7K3ZAHPHymM/download/eoelab.org.crt && \
    cp eoelab.org.crt /usr/local/share/ca-certificates/eoelab.org.crt && \
    update-ca-certificates && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

RUN useradd coder \
        --create-home \
        --shell=/bin/bash \
        --uid=1000 \
        --user-group && \
    echo "coder ALL=(ALL) NOPASSWD:ALL" >>/etc/sudoers.d/nopasswd

ENV LANG en_US.UTF-8
USER coder