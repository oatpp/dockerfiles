FROM ubuntu:18.04

RUN apt-get update
RUN apt-get -y --fix-missing upgrade

RUN apt-get -y install build-essential

RUN apt-get -y install cmake

RUN apt-get -y install wget

RUN apt-get -y install pkg-config

RUN apt-get -y install git

#############################################
## Get and install libressl-2.9.0

WORKDIR /deps/libressl/

RUN wget https://ftp.openbsd.org/pub/OpenBSD/LibreSSL/libressl-2.9.0.tar.gz
RUN tar -xvzf libressl-2.9.0.tar.gz

WORKDIR /deps/libressl/libressl-2.9.0

RUN cmake .
RUN make
RUN make install

#############################################
## sudo is needed for CI agent

RUN apt-get -y install sudo