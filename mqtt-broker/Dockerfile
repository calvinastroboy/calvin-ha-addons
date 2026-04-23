ARG BUILD_FROM
FROM $BUILD_FROM

# Install mosquitto
RUN apk add --no-cache mosquitto mosquitto-clients

# Copy rootfs
COPY rootfs /

# Use S6 overlay
ENTRYPOINT ["/init"]
