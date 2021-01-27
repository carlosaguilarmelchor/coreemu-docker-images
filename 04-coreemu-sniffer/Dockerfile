# docker base image for coreemu with basic terminal, networking and sniffing tools

FROM coreemu-termnettools

RUN set -e -x \
    && export DEBIAN_FRONTEND=noninteractive \
    && apt-get update \
    && apt-get -y upgrade \
#
# install network sniffing tools
#
    && apt-get -y --no-install-recommends install \
        tcpdump termshark tcpflow \ 
#
# finish installation
#
    && rm -rf /var/lib/apt/lists/*
