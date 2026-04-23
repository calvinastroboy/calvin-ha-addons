ARG BUILD_FROM
FROM koenkk/zigbee2mqtt:latest

# Install bashio for config handling
RUN apk add --no-cache curl jq

# Copy rootfs
COPY rootfs /

# Use S6 overlay (keep original entrypoint for S6)
ENTRYPOINT ["/init"]
