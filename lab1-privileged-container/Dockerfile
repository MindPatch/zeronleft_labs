FROM alpine:latest

# Install useful tools for the lab
RUN apk add --no-cache \
    bash \
    util-linux \
    coreutils \
    e2fsprogs \
    grep \
    sed \
    findmnt

# Create a simple indicator file
RUN echo "You are inside the container" > /container_marker

# Set bash as default shell
CMD ["/bin/bash"]
