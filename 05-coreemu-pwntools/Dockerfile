# docker base image for coreemu with basic terminal, networking sniffing and pwn tools

FROM coreemu-sniffer

RUN set -e -x \
    && export DEBIAN_FRONTEND=noninteractive \
    && apt-get update \
    && apt-get -y upgrade \
#
# install pwntools
#
    && apt-get -y --no-install-recommends install ipython3 \
        python3-pip python3-dev git libssl-dev \ 
        libffi-dev build-essential \ 
    && python3 -m pip install --upgrade pip \
    && python3 -m pip install --upgrade pwntools \
#
# finish installation
#
    && rm -rf /var/lib/apt/lists/* \
    && rm -rf /root/.cache/pip
