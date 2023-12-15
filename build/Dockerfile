FROM ubuntu:22.04

ARG NORDVPN_VERSION=${NORDVPN_VERSION:-3.16.5}
ARG DEBIAN_FRONTEND=noninteractive

RUN apt-get update && \
    apt-get install -y curl iputils-ping wireguard-tools jq && \
    curl https://repo.nordvpn.com/deb/nordvpn/debian/pool/main/nordvpn-release_1.0.0_all.deb -o "/tmp/nordrepo.deb" && \
    apt-get install -y /tmp/nordrepo.deb && \
    apt-get update && \
    apt-get install -y nordvpn${NORDVPN_VERSION:+=$NORDVPN_VERSION} && \
    apt-get remove -y wget nordvpn-release && \
    rm /tmp/nordrepo.deb && \
    apt-get clean

COPY get_wireguard_config.sh ./get_wireguard_config.sh

ENTRYPOINT /etc/init.d/nordvpn start && sleep 5 && /bin/bash -c "$@"
CMD ./get_wireguard_config.sh
