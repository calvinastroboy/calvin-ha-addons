ARG BUILD_FROM
FROM $BUILD_FROM

# Install Filebrowser
RUN apk add --no-cache curl jq && \
    FILEBROWSER_VERSION=$(curl -s https://api.github.com/repos/filebrowser/filebrowser/releases/latest | jq -r .tag_name) && \
    if [ "$(uname -m)" = "aarch64" ]; then FB_ARCH=linux-arm64; \
    elif [ "$(uname -m)" = "x86_64" ]; then FB_ARCH=linux-amd64; \
    elif [ "$(uname -m)" = "armv7l" ]; then FB_ARCH=linux-armv7; \
    elif [ "$(uname -m)" = "armv6l" ]; then FB_ARCH=linux-armv6; \
    else FB_ARCH=linux-amd64; fi && \
    curl -L -o /tmp/filebrowser.tar.gz \
    "https://github.com/filebrowser/filebrowser/releases/download/${FILEBROWSER_VERSION}/filebrowser-${FB_ARCH}.tar.gz" && \
    tar -xzf /tmp/filebrowser.tar.gz -C /usr/local/bin/ && \
    chmod +x /usr/local/bin/filebrowser && \
    rm -rf /tmp/*

# Copy rootfs
COPY rootfs /

# Use S6 overlay
ENTRYPOINT ["/init"]
