FROM debian:latest@sha256:df6ebd5e9c87d0d7381360209f3a05c62981b5c2a3ec94228da4082ba07c4f05
MAINTAINER Grammy Jiang <grammy.jiang@gmail.com>

# Auto redirect to the fastest mirror
# ENV DEBIAN_MIRROR http://httpredir.debian.org/debian

# China
ENV DEBIAN_MIRROR http://ftp2.cn.debian.org/debian

RUN mv /etc/apt/sources.list /etc/apt/sources.list.bak \
 && echo "deb $DEBIAN_MIRROR jessie main" > /etc/apt/sources.list \
 && echo "deb $DEBIAN_MIRROR jessie-updates main" >> /etc/apt/sources.list \
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
 && curl -sSL http://radsite.lbl.gov/radiance/dist/rad5R0all.tar.gz -o rad5R0all.tar.gz \
 && tar xf rad5R0all.tar.gz
