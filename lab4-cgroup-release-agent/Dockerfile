FROM ubuntu:22.04

# Install necessary tools
RUN apt-get update && apt-get install -y \
    bash \
    coreutils \
    util-linux \
    procps \
    grep \
    sed \
    gawk \
    && rm -rf /var/lib/apt/lists/*

# Create marker
RUN echo "Cgroup escape lab container" > /container_marker

WORKDIR /workspace

CMD ["/bin/bash"]
