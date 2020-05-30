FROM lganzzzo/alpine-cmake:latest

#######################################################
## MongoCXX

RUN apk update
RUN apk add python
RUN apk add openssl-dev
RUN apk add perl

WORKDIR /download
RUN git clone https://github.com/mongodb/mongo-c-driver.git --branch r1.17 --depth 1 \
  && cd mongo-c-driver \
  && mkdir cmake-build && cd cmake-build \
  && cmake -DENABLE_AUTOMATIC_INIT_AND_CLEANUP=OFF -DCMAKE_BUILD_TYPE=Release -DCMAKE_INSTALL_PREFIX=/usr/local -DBUILD_SHARED_LIBS=OFF -DENABLE_TESTS=OFF .. \
  && make install -j $(nproc)

WORKDIR /download
RUN git clone https://github.com/mongodb/mongo-cxx-driver.git --branch releases/stable --depth 1 \
  && cd mongo-cxx-driver/build \
  && cmake -DCMAKE_BUILD_TYPE=Release -DBUILD_SHARED_LIBS=OFF -DCMAKE_PREFIX_PATH=/usr/local -DCMAKE_INSTALL_PREFIX=/usr/local -DCMAKE_TESTING_ENABLED=OFF .. \
  && make install -j $(nproc)
