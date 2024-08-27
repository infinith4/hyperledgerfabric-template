FROM --platform=linux/amd64 mcr.microsoft.com/devcontainers/base:jammy

# [Optional] Uncomment this section to install additional OS packages.
RUN apt-get update && export DEBIAN_FRONTEND=noninteractive \
     && apt-get -y install --no-install-recommends sudo curl

# ENV TZ=Asia/Tokyo LANG=ja_JP.UTF-8 LANGUAGE=ja_JP:ja



# shellをbashに変更
SHELL [ "/bin/bash", "-c" ]

#### install nvm
RUN curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.7/install.sh | bash

#### install node
RUN . $HOME/.nvm/nvm.sh && \
    nvm install --lts && \
    nvm use --lts && \
    node -v && npm -v && \
    npm i -g yarn

