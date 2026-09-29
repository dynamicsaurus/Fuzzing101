FROM mcr.microsoft.com/devcontainers/base:ubuntu-20.04

ENV DEBIAN_FRONTEND=noninteractive

# Install AFL++ build dependencies and toolchain
RUN apt-get update && apt-get install -y --no-install-recommends \
    build-essential \
    python3-dev \
    python3-pip \
    automake \
    cmake \
    git \
    flex \
    bison \
    libglib2.0-dev \
    libpixman-1-dev \
    clang \
    llvm \
    llvm-dev \
    lld \
    gdb \
    && apt-get clean && rm -rf /var/lib/apt-lists/*

# Clone, compile, and install AFL++
RUN git clone https://github.com/AFLplusplus/AFLplusplus.git /tmp/AFLplusplus \
    && cd /tmp/AFLplusplus \
    && make source-only \
    && make install \
    && rm -rf /tmp/AFLplusplus
