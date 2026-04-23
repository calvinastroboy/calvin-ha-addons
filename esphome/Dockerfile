ARG BUILD_FROM
FROM esphome/esphome:2024.10.0

# Install bashio
RUN apt-get update && apt-get install -y --no-install-recommends \
    curl \
    jq \
    && rm -rf /var/lib/apt/lists/* \
    && curl -J -L -o /tmp/bashio.tar.gz \
    "https://github.com/hassio-addons/bashio/archive/v0.16.0.tar.gz" \
    && mkdir -p /tmp/bashio \
    && tar zxvf /tmp/bashio.tar.gz -C /tmp/bashio --strip-components=1 \
    && mv /tmp/bashio/lib /usr/lib/bashio \
    && ln -s /usr/lib/bashio/bashio /usr/bin/bashio \
    && rm -rf /tmp/bashio.tar.gz /tmp/bashio

# Copy rootfs
COPY rootfs /

# Use S6 overlay
ENTRYPOINT ["/init"]
