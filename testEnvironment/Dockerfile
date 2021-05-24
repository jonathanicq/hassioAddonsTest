ARG BUILD_FROM
FROM $BUILD_FROM

VOLUME [ "/data" ]

#Install last version https://github.com/dvershinin/lastversion
RUN \
    apk add --no-cache build-base git moreutils gcc g++ musl-dev python3-dev libffi-dev openssl-dev cargo \
    && pip install --upgrade pip \
    && pip install -U pip \
    && git clone https://github.com/jonathanicq/hassioAddonsTest \
    && cd /testEnvironment \
    && python3 -m pip install -r requirements.txt
 
# Copy files
COPY rootfs/ /testEnvironment/
RUN chmod a+x /testEnvironment/run.sh
WORKDIR [ "/testEnvironment" ] 
CMD [ "/testEnvironment/start.sh" ] 

# Set shell
SHELL ["/bin/bash", "-o", "pipefail", "-c"]
