# docker base image for coreemu with basic terminal, networking sniffing scapy and pwn tools

FROM coreemu-pwntools

RUN set -e -x \
    && export DEBIAN_FRONTEND=noninteractive \
    && apt-get update \
    && apt-get -y upgrade \
#
# install pwntools
#
    && python3 -m pip install --upgrade pip \
    && python3 -m pip install --pre --upgrade scapy \
#
# finish installation
#
    && rm -rf /var/lib/apt/lists/* \
    && rm -rf /root/.cache/pip
