# docker base image for coreemu with basic terminal tools

FROM coreemu-base

RUN set -e -x \
    && export DEBIAN_FRONTEND=noninteractive \
    && apt-get update \
    && apt-get -y upgrade \
#
# install basic terminal tools
#
    && apt-get -y --no-install-recommends install \
        dumb-init procps nano vim-tiny tmux \
#
# finish installation
#
    && rm -rf /var/lib/apt/lists/*
