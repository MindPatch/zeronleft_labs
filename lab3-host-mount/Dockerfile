FROM alpine:latest

# Install tools needed for exploitation
RUN apk add --no-cache \
    bash \
    coreutils \
    openssh-client \
    openssl \
    gcc \
    musl-dev \
    util-linux

# Create marker
RUN echo "Container with host filesystem mounted" > /container_marker

WORKDIR /workspace

CMD ["/bin/bash"]
