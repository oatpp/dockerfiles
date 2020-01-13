FROM ubuntu:18.04

RUN apt-get update
RUN apt-get -y --fix-missing upgrade

RUN apt-get -y install build-essential
RUN apt-get -y install cmake
RUN apt-get -y install git
RUN apt-get -y install wget
RUN apt-get -y install pkg-config

RUN apt-get -y install sudo

#---------------------------------------------------------------
# install mimalloc

WORKDIR /inst

RUN git clone -b v1.2.2 https://github.com/microsoft/mimalloc

WORKDIR /inst/mimalloc/build

RUN cmake -DCMAKE_BUILD_TYPE=Release ..
RUN make install
