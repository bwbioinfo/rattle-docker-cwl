# Use the official Ubuntu 20.04 image as the base image
FROM ubuntu:20.04

# Update package lists and install essential build tools
RUN apt-get update && apt-get install -y \
    build-essential

# Set the timezone to UTC non-interactively
RUN DEBIAN_FRONTEND=noninteractive TZ=Etc/UTC apt-get -y install tzdata

# Update package lists again and install additional required packages
RUN apt-get update && apt-get install -y \
    git \
    zlib1g-dev \
    cmake

# Set the working directory to /opt/
WORKDIR /opt/

# Clone the RATTLE repository and its submodules from GitHub
RUN git clone --recurse-submodules https://github.com/comprna/RATTLE

# Change the working directory to the cloned RATTLE directory
WORKDIR /opt/RATTLE

# Execute the build script for RATTLE
RUN ./build.sh

# Add the RATTLE installation directory to the PATH environment variable
# This allows the RATTLE commands to be run from anywhere in the terminal
ENV PATH="/opt/RATTLE:${PATH}"

CMD [ "rattle" ]