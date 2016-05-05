FROM alpine:3.3
MAINTAINER Morgan Auchede <morgan.auchede@gmail.com>

ENV \
    BEANSTALKD_VERSION=1.10

RUN set -x \

    # Prepare system

    && apk add -U \

    # Install packages

    && BUILD_DEPS="curl gcc make musl-dev tar" \

    && apk add \
           $BUILD_DEPS \

    # Install beanstalkd

    && curl -ksL "https://github.com/kr/beanstalkd/archive/v$BEANSTALKD_VERSION.tar.gz" | tar fxz - -C /tmp \
    && sed -i "s|#include <sys/fcntl.h>|#include <fcntl.h>|g" /tmp/beanstalkd-$BEANSTALKD_VERSION/sd-daemon.c \

    && make -C /tmp/beanstalkd-$BEANSTALKD_VERSION \
    && make -C /tmp/beanstalkd-$BEANSTALKD_VERSION install PREFIX=/usr \

    # Clean

    && apk del \
           $BUILD_DEPS \

    && rm -rf \
           /tmp/* \
           /var/cache/apk/*

COPY ./rootfs /

ENTRYPOINT [ "/entrypoint.sh" ]
