FROM ubuntu:20.04

RUN apt-get update && apt-get install -y \
    build-essential

RUN DEBIAN_FRONTEND=noninteractive TZ=Etc/UTC apt-get -y install tzdata

RUN apt-get update && apt-get install -y \
    git \
    zlib1g-dev \ 
    cmake

WORKDIR /opt/

RUN git clone --recurse-submodules https://github.com/comprna/RATTLE

WORKDIR /opt/RATTLE

RUN ./build.sh

CMD [ "/opt/RATTLE/rattle" ]
