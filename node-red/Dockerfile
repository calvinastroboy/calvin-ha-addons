ARG BUILD_FROM
FROM nodered/node-red:latest

USER root

# Install additional system packages and Python
RUN apk add --no-cache \
    jq \
    python3 \
    py3-pip \
    make \
    g++ \
    linux-headers

# Install bashio
RUN curl -J -L -o /tmp/bashio.tar.gz \
    "https://github.com/hassio-addons/bashio/archive/v0.16.0.tar.gz" \
    && mkdir -p /tmp/bashio \
    && tar zxvf /tmp/bashio.tar.gz -C /tmp/bashio --strip-components=1 \
    && mv /tmp/bashio/lib /usr/lib/bashio \
    && ln -s /usr/lib/bashio/bashio /usr/bin/bashio \
    && rm -rf /tmp/bashio.tar.gz /tmp/bashio

# Copy rootfs
COPY rootfs /

# Set proper permissions
RUN chmod +x /etc/services.d/node-red/run

# Switch back to node-red user
USER node-red

ENTRYPOINT ["/init"]
