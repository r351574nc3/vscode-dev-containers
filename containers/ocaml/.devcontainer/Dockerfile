# See here for image contents: https://github.com/microsoft/vscode-dev-containers/tree/v0.183.0/containers/debian/.devcontainer/base.Dockerfile

# [Choice] Debian version: buster, stretch
ARG VARIANT="buster"
FROM mcr.microsoft.com/vscode/devcontainers/base:0-${VARIANT}

# ** [Optional] Uncomment this section to install additional packages. **
RUN apt-get update && export DEBIAN_FRONTEND=noninteractive \
     && apt-get -y install --no-install-recommends \
            sudo \
            pkg-config \
            git \
            build-essential \
            m4 \
            software-properties-common \
            aspcud \
            unzip \
            rsync \
            curl \
            dialog \
            nano \
            libx11-dev \
            ocaml \
            ocaml-native-compilers \
            camlp4-extra \
            opam \
            rsync \
    && apt-get clean -y

ENV PATH=$PATH:$HOME/.opam/system/bin/

RUN opam init \
    && eval `opam config env` \
    && source $HOME/.opam/opam-init/init.sh > /dev/null 2> /dev/null || true \
    && opam install dune \
    && opam install ocamlfind
