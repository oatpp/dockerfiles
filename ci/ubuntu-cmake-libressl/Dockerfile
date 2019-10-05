FROM lganzzzo/ubuntu-cmake:latest

RUN apt-get update
RUN apt-get -y --fix-missing upgrade

RUN apt-get -y install wget

RUN apt-get -y install pkg-config

#############################################
## Get and install libressl-2.9.0

WORKDIR /deps/libressl/

RUN wget https://ftp.openbsd.org/pub/OpenBSD/LibreSSL/libressl-2.9.0.tar.gz
RUN tar -xvzf libressl-2.9.0.tar.gz

WORKDIR /deps/libressl/libressl-2.9.0

RUN cmake .
RUN make
RUN make install
