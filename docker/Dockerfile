# Use the official Ubuntu base image
FROM ubuntu:latest

# Update the package list and install necessary packages
RUN apt-get update && apt-get install -y \
    build-essential \
    wget \
    curl \
    zlib1g-dev \
    git \
    && rm -rf /var/lib/apt/lists/*

# Set the working directory
WORKDIR /opt
RUN git clone https://github.com/weizhongli/cdhit.git
WORKDIR /opt/cdhit
RUN make

# Add the cd-hit binary to the PATH
ENV PATH="/opt/cdhit:${PATH}"