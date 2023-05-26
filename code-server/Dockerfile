FROM eoelab.org:1032/build-image-stacks/coder-workspace-stacks/coder:base

LABEL maintainer="eoelab <eoelab@eoelab.org>"

EXPOSE 8080

RUN cd /home/coder && \
    wget http://eoelab.org:1024/index.php/s/s6ofW8srtTxbN3z/download/code-server_4.13.0_amd64.deb && \
    sudo dpkg -i code-server_4.13.0_amd64.deb && \
    sudo systemctl enable --now code-server@coder && \
    rm code-server_4.13.0_amd64.deb