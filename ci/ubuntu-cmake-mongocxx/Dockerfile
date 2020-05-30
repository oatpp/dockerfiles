FROM lganzzzo/ubuntu-cmake:latest

#######################################################
## MongoCXX

RUN apt-get update
RUN apt-get install -y python
RUN apt-get install -y libssl-dev
RUN apt-get install -y perl

#RUN apt-get install -y libmongoc-1.0-0

WORKDIR /download
#RUN git clone https://github.com/mongodb/mongo-c-driver.git --branch r1.14 --depth 1 \
#  && cd mongo-c-driver \
#  && mkdir cmake-build && cd cmake-build \
#  && cmake -DENABLE_AUTOMATIC_INIT_AND_CLEANUP=OFF -DCMAKE_BUILD_TYPE=Release -DCMAKE_INSTALL_PREFIX=/usr/local -DBUILD_SHARED_LIBS=OFF -DENABLE_TESTS=OFF .. \
#  && make install -j $(nproc)
#&& python build/calc_release_version.py > VERSION_CURRENT \

RUN git clone https://github.com/mongodb/mongo-c-driver.git --branch r1.17 --depth 1 \
  && cd mongo-c-driver \
  && echo "1.17.0" > VERSION_CURRENT \
  && mkdir cmake-build && cd cmake-build \
  && cmake -DENABLE_AUTOMATIC_INIT_AND_CLEANUP=OFF -DCMAKE_BUILD_TYPE=Release -DCMAKE_INSTALL_PREFIX=/usr/local -DBUILD_SHARED_LIBS=OFF -DENABLE_TESTS=OFF .. \
  && make install -j $(nproc)

WORKDIR /download
RUN git clone https://github.com/mongodb/mongo-cxx-driver.git --branch releases/v3.5 --depth 1 \
  && cd mongo-cxx-driver/build \
  && cmake -DCMAKE_BUILD_TYPE=Release -DBUILD_SHARED_LIBS=OFF -DCMAKE_PREFIX_PATH=/usr/local -DCMAKE_INSTALL_PREFIX=/usr/local -DCMAKE_TESTING_ENABLED=OFF .. \
  && make install -j $(nproc)
