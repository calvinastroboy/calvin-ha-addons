ARG BUILD_FROM
FROM $BUILD_FROM

# Install FRP client
ARG FRP_VERSION=v0.61.0
RUN apk add --no-cache curl jq && \
    if [ "$(uname -m)" = "aarch64" ]; then FRP_ARCH=arm64; \
    elif [ "$(uname -m)" = "x86_64" ]; then FRP_ARCH=amd64; \
    elif [ "$(uname -m)" = "armv7l" ]; then FRP_ARCH=armv7; \
    elif [ "$(uname -m)" = "armv6l" ]; then FRP_ARCH=arm; \
    else FRP_ARCH=amd64; fi && \
    curl -L -o /tmp/frp.tar.gz \
    "https://github.com/fatedier/frp/releases/download/${FRP_VERSION}/frp_${FRP_VERSION#v}_linux_${FRP_ARCH}.tar.gz" && \
    tar -xzf /tmp/frp.tar.gz -C /tmp && \
    cp /tmp/frp_*/frpc /usr/local/bin/frpc && \
    chmod +x /usr/local/bin/frpc && \
    rm -rf /tmp/frp*

# Copy rootfs
COPY rootfs /

# Use S6 overlay
ENTRYPOINT ["/init"]