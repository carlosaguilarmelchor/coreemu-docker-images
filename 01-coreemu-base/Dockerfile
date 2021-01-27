# docker base image for coreemu

FROM ubuntu:20.04

RUN set -e -x \
    && export DEBIAN_FRONTEND=noninteractive \
    && apt-get update \
    && apt-get -y upgrade \
#
# install core-net mandatory tools and ssh server
#
    && apt-get -y --no-install-recommends install \
        iproute2 ethtool dropbear \
#
# finish installation
#
    && rm -rf /var/lib/apt/lists/*
# Add PATH for root login on dropbear
RUN echo '#!/bin/sh \nif [ "$SSH_CONNECTION" ]; then . /etc/environment; fi' >> /etc/profile.d/ssh_login.sh
