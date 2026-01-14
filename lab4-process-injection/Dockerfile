FROM ubuntu:22.04

RUN apt-get update && apt-get install -y \
    gdb \
    strace \
    ltrace \
    procps \
    python3 \
    python3-pip \
    binutils \
    && rm -rf /var/lib/apt/lists/*

RUN pip3 install pwntools

WORKDIR /workspace

CMD ["/bin/bash"]
