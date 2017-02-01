FROM debian:latest
MAINTAINER Grammy Jiang <grammy.jiang@gmail.com>

RUN mv /etc/apt/sources.list /etc/apt/sources.list.bak \
 && echo "deb http://httpredir.debian.org/debian jessie main" > /etc/apt/sources.list \
 && echo "deb http://httpredir.debian.org/debian jessie-updates main" >> /etc/apt/sources.list \
 && echo "deb http://security.debian.org jessie/updates main" >> /etc/apt/sources.list \
 && set -x \
 && apt-get update \
 && apt-get install -q -y \
    csh \
    curl \
    file \
    g++ \
    gcc \
    libx11-dev \
    make \
    vim \
    wish

RUN set -x \
 && mkdir -p /root/downloads/ \
 && cd /root/downloads/ \
 && curl -sSL http://radsite.lbl.gov/radiance/dist/rad5R0all.tar.gz | tar xf
