FROM plantuml/plantuml-server:jetty

ARG INSTALL_ZSH=false
ARG USERNAME=root
ARG USER_UID=0
ARG USER_GID=$USER_UID

USER root
RUN apt-get update && apt-get install -y git 
RUN git clone --depth 1 https://github.com/microsoft/vscode-dev-containers.git \
    && bash vscode-dev-containers/script-library/common-debian.sh "${INSTALL_ZSH}" "${USERNAME}" "${USER_UID}" "${USER_GID}" \
    && rm -rf vscode-dev-containers

WORKDIR /workspace