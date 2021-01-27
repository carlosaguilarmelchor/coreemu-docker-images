# docker base image for coreemu with basic terminal and networking tools

FROM coreemu-termtools

RUN set -e -x \
    && export DEBIAN_FRONTEND=noninteractive \
    && apt-get update \
    && apt-get -y upgrade \
#
# install basic networking tools
#
    && apt-get -y --no-install-recommends install \
        iperf3 knot-host mtr-tiny openssh-client ncat socat \
        net-tools iproute2 ifupdown inetutils-ping tcpdump \
        telnet traceroute wget curl ca-certificates \
#
# finish installation
#
    && ln -s /usr/bin/khost /usr/local/bin/host \
    && rm -rf /var/lib/apt/lists/*
