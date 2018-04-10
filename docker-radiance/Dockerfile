FROM debian:latest@sha256:c908a4fcb2b2a1953bd40ebc12d9a4116868d72540efc27502ee6c2395b8a1e9
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
