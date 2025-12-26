# Use Ubuntu as the base image
FROM ubuntu:20.04-slim

# Install necessary packages
RUN apt-get update && apt-get install -y \
    python3-pip \
    python3-setuptools \
    python3-dev \
    openjdk-8-jdk \
    git \
    zip \
    unzip \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*

# Install any additional dependencies if needed
RUN pip3 install --upgrade pip

# Create a non-root user (coder) with UID 1000  
RUN useradd -m -s /bin/bash coder \
  && echo "coder ALL=(ALL) NOPASSWD:ALL" > /etc/sudoers.d/coder \
  && chmod 0440 /etc/sudoers.d/coder

USER coder 
WORKDIR /workspaces
