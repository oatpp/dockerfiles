FROM ubuntu:18.04

RUN apt-get update
RUN apt-get -y --fix-missing upgrade

RUN apt-get -y install build-essential

RUN apt-get -y install cmake

RUN apt-get -y install wget

RUN apt-get -y install pkg-config

RUN apt-get -y install git

RUN apt-get -y install libssl-dev


#############################################
## download curl-7.63.0

WORKDIR /deps/curl/

RUN wget https://curl.haxx.se/download/curl-7.63.0.tar.gz

#############################################
## unpack

RUN tar -xvzf curl-7.63.0.tar.gz

#############################################
## build and install libressl

WORKDIR /deps/curl/curl-7.63.0

RUN cmake .
RUN make
RUN make install
