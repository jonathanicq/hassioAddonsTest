ARG BUILD_FROM=homeassistant/amd64-base:latest
FROM $BUILD_FROM

ENV LANG C.UTF-8

VOLUME [ "/data" ]
#COPY start.sh /addons/start.sh
# Copy script
COPY run.sh /
RUN chmod a+x /run.sh
CMD [ "/start.sh"] 

ENTRYPOINT ["/start.sh"]

LABEL io.hass.version="VERSION" io.hass.type="addon" io.hass.arch="armhf|aarch64|i386|amd64"
