ARG BUILD_FROM
FROM ghcr.io/meeb/tubesync:latest

VOLUME [ "/config" ]

#RUN sed -i 's/Path('\''\/'\'')/Path('\''\/config\/addons_config\/tubesync'\'')/' /app/tubesync/local_settings.py 
#RUN sed -i 's/DOWNLOADS_BASE_DIR = BASE_DIR/DOWNLOADS_BASE_DIR = \/share\/tubesync/g' /app/tubesync/local_settings.py 	
RUN sed -i 's/DOWNLOADS_BASE_DIR = BASE_DIR/DOWNLOADS_BASE_DIR = \/config\/tubesync\/tubesync/g' /app/tubesync/local_settings.py 
RUN sed -i 's/CONFIG_BASE_DIR = BASE_DIR/CONFIG_BASE_DIR = \/config\/tubesync\/tubesync/g' /app/tubesync/local_settings.py
 
### LABELS
ARG BUILD_ARCH
ARG BUILD_DATE
ARG BUILD_DESCRIPTION
ARG BUILD_NAME
ARG BUILD_REF
ARG BUILD_REPOSITORY
ARG BUILD_VERSION
LABEL \
    io.hass.name="${BUILD_NAME}" \
    io.hass.description="${BUILD_DESCRIPTION}" \
    io.hass.arch="${BUILD_ARCH}" \
    io.hass.type="addon" \
    io.hass.version=${BUILD_VERSION} \
    maintainer="jdeath (https://github.com/jdeath)" \
    org.opencontainers.image.title="${BUILD_NAME}" \
    org.opencontainers.image.description="${BUILD_DESCRIPTION}" \
    org.opencontainers.image.vendor="Home Assistant Add-ons" \
    org.opencontainers.image.authors="jdeath (https://github.com/jdeath)" \
    org.opencontainers.image.licenses="MIT" \
    org.opencontainers.image.url="https://github.com/jdeath" \
    org.opencontainers.image.source="https://github.com/${BUILD_REPOSITORY}" \
    org.opencontainers.image.documentation="https://github.com/${BUILD_REPOSITORY}/blob/main/README.md" \
    org.opencontainers.image.created=${BUILD_DATE} \
    org.opencontainers.image.revision=${BUILD_REF} \
    org.opencontainers.image.version=${BUILD_VERSION}
