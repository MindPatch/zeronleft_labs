FROM docker:latest

# Install additional tools
RUN apk add --no-cache \
    bash \
    curl \
    jq \
    git

# Add a marker
RUN echo "Container with Docker socket access" > /container_marker

# Create helpful script
RUN echo '#!/bin/bash' > /check_socket.sh && \
    echo 'echo "=== Docker Socket Check ==="' >> /check_socket.sh && \
    echo 'if [ -S /var/run/docker.sock ]; then' >> /check_socket.sh && \
    echo '    echo "[+] Docker socket is mounted!"' >> /check_socket.sh && \
    echo '    ls -la /var/run/docker.sock' >> /check_socket.sh && \
    echo '    echo ""' >> /check_socket.sh && \
    echo '    echo "[*] Testing access..."' >> /check_socket.sh && \
    echo '    if docker ps >/dev/null 2>&1; then' >> /check_socket.sh && \
    echo '        echo "[+] Docker socket is accessible!"' >> /check_socket.sh && \
    echo '        echo "[!] This container can control the host Docker daemon!"' >> /check_socket.sh && \
    echo '    else' >> /check_socket.sh && \
    echo '        echo "[-] Docker socket exists but is not accessible"' >> /check_socket.sh && \
    echo '    fi' >> /check_socket.sh && \
    echo 'else' >> /check_socket.sh && \
    echo '    echo "[-] Docker socket is NOT mounted"' >> /check_socket.sh && \
    echo 'fi' >> /check_socket.sh && \
    chmod +x /check_socket.sh

WORKDIR /workspace

CMD ["/bin/bash"]
