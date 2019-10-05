FROM lganzzzo/ubuntu-cmake:latest

RUN apt-get update
RUN apt-get -y --fix-missing upgrade

RUN apt-get -y install pkg-config

RUN apt-get -y install wget

#############################################
## Get and install postgresql-11.1

WORKDIR /deps/postgresql/

RUN wget https://ftp.postgresql.org/pub/source/v11.1/postgresql-11.1.tar.gz

RUN tar -xvzf postgresql-11.1.tar.gz

WORKDIR /deps/postgresql/postgresql-11.1

RUN ./configure --without-readline --without-zlib
RUN make
RUN make install
