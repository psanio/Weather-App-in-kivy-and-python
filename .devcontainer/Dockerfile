# Use Ubuntu as the base image
FROM ubuntu:18.04

# Install necessary packages
RUN apt-get update && export DEBIAN_FRONTEND=noninteractive && apt-get install -y \
    sudo ssh ca-certificates curl gnupg build-essential git zip unzip \
    python3-pip python3-setuptools python3-dev python3-wheel \
    openjdk-8-jdk cython3 \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*

# Install any additional dependencies if needed
RUN pip3 install --upgrade pip

# Setup cython link
RUN update-alternatives --install /usr/bin/cython cython /usr/bin/cython3 1

# Create a non-root user (coder) with UID 1000  
RUN useradd -m -s /bin/bash coder \
  && echo "coder ALL=(ALL) NOPASSWD:ALL" > /etc/sudoers.d/coder \
  && chmod 0440 /etc/sudoers.d/coder

USER coder 
WORKDIR /workspaces
