FROM debian:jessie

RUN apt-get update && apt-get install -y \
    sudo \
    git \
    nano \
    locales


RUN dpkg-reconfigure locales && \
    locale-gen C.UTF-8 && \
    /usr/sbin/update-locale LANG=C.UTF-8

ENV LC_ALL C.UTF-8