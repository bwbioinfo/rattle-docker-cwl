FROM ubuntu:24.04

RUN apt-get update && apt-get install -y \
    build-essential \
    cmake \
    git \
    libboost-all-dev \
    libeigen3-dev \
    libgsl-dev \
    libhdf5-dev \
    libtbb-dev \
    python3 \
    python3-pip \
    wget

WORKDIR /opt/

RUN git clone --recurse-submodules https://github.com/comprna/RATTLE

WORKDIR /opt/RATTLE

RUN ./build.sh

CMD [ "/opt/RATTLE/rattle" ]
