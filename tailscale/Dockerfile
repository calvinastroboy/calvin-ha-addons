ARG BUILD_FROM
FROM $BUILD_FROM

# Install Tailscale
ARG TAILSCALE_VERSION=1.76.0
RUN apk add --no-cache curl iptables ip6tables jq \
    && if [ "$(uname -m)" = "aarch64" ]; then TS_ARCH=arm64; \
    elif [ "$(uname -m)" = "x86_64" ]; then TS_ARCH=amd64; \
    elif [ "$(uname -m)" = "armv7l" ]; then TS_ARCH=arm; \
    elif [ "$(uname -m)" = "armv6l" ]; then TS_ARCH=arm; \
    else TS_ARCH=amd64; fi \
    && curl -fsSL -o /tmp/tailscale.tgz \
    "https://pkgs.tailscale.com/stable/tailscale_${TAILSCALE_VERSION}_${TS_ARCH}.tgz" \
    && tar xzf /tmp/tailscale.tgz -C /tmp \
    && cp /tmp/tailscale_*/tailscale /usr/local/bin/tailscale \
    && cp /tmp/tailscale_*/tailscaled /usr/local/bin/tailscaled \
    && rm -rf /tmp/tailscale*

# Copy rootfs
COPY rootfs /

# Use S6 overlay
ENTRYPOINT ["/init"]
