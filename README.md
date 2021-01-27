# coreemu-docker-images repository

This repository contains a set of docker images for [CORE](https://github.com/coreemu/core) and a script to (re)build them all.

## Usage

Clone the repo.

Run ```./generate_images```.

## Image list

All containers are derived from an Ubuntu 20.04 (minimal) container

### coreemu-base

This is a basic container with iproute2 and ethtool for CORE compatibility and dropbear as a lightweight SSH server.

### coreemu-termtools

This image builds upon coreemu-base by adding terminal tools:
  * dumb-init procps for process management;
  * nano vim-tiny for file editing;
  * tmux to handle multiple terminal windows with a single terminal connected to the container.

### coreemu-termnettools

This image builds upon coreemu-termtools by adding networking tools:
  * knot-host; for DNS
  * iperf3 mtr-tiny net-tools iproute2 ifupdown inetutils-ping tcpdump for network testing/administration;
  * openssh-client ncat socat telnet wget curl ca-certificates to act as client/server for different protocols.

### coreemu-sniffer

This image builds upon coreemu-termnettools by adding more advanced sniffing toosl:
  * termshark (and tshark implicitly) for command-line/terminal usage of wireshark;
  * tcpflow as a simple tcp flow reconstruction utility. 

### coreemu-pwntools

This image builds upon coreemu-sniffer by adding a CTF tool:
  * [pwntools](https://github.com/Gallopsled/pwntools);
  * and associated dependencies/recommendations (among which ipython3 python3-pip git and build-essential).

### coreemu-attacker

This image builds upon coreemu-pwntools by adding the packet crafting tool [scapy](https://scapy.net/).
