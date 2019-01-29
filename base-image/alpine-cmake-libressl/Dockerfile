FROM lganzzzo/alpine-cmake:latest

RUN apk add wget
RUN apk add linux-headers

WORKDIR /deps/

RUN wget https://ftp.openbsd.org/pub/OpenBSD/LibreSSL/libressl-2.9.0.tar.gz
RUN tar -xvzf libressl-2.9.0.tar.gz
WORKDIR /deps/libressl-2.9.0

RUN cmake .
RUN make
RUN make install
