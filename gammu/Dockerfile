ARG BUILD_FROM=ghcr.io/home-assistant/amd64-base:3.19
FROM ${BUILD_FROM}

# Set environment variables for UTF-8 support
ENV LANG C.UTF-8

# Install system dependencies and Python tooling
RUN apk update \
  && apk add --no-cache \
    python3 \
    py3-pip \
    gammu \
    gammu-dev \
  && pip3 install --no-cache-dir -U setuptools wheel \
  && pip3 install --no-cache-dir py-smsgateway-async \
  && rm -rf /var/cache/apk/*

# Copy root filesystem
COPY rootfs /
