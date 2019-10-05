FROM lganzzzo/ubuntu-cmake:latest

RUN apt-get update
RUN apt-get -y --fix-missing upgrade

RUN apt-get -y install wget

RUN apt-get -y install pkg-config

RUN apt-get -y install libssl-dev


#############################################
## download curl-7.63.0

WORKDIR /deps/curl/

RUN wget https://curl.haxx.se/download/curl-7.63.0.tar.gz
RUN tar -xvzf curl-7.63.0.tar.gz

WORKDIR /deps/curl/curl-7.63.0

RUN cmake .
RUN make
RUN make install
