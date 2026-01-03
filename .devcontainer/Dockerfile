FROM mcr.microsoft.com/devcontainers/base:ubuntu18.04
ENV DEBIAN_FRONTEND=noninteractive 

RUN apt-get update \
  && apt-get install -y --no-install-recommends unzip \
  ca-certificates curl gnupg build-essential git python3 python3-venv python3-pip xz-utils sudo ssh \
  && rm -rf /var/lib/apt/lists/*

# Create a non-root user (coder) with UID 1000  
RUN useradd -m -s /bin/bash coder \
  && echo "coder ALL=(ALL) NOPASSWD:ALL" > /etc/sudoers.d/coder \
  && chmod 0440 /etc/sudoers.d/coder

USER coder 
