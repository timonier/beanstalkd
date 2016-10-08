FROM alpine:3.4
MAINTAINER Morgan Auchede <morgan.auchede@gmail.com>

ENV \
    BEANSTALKD_VERSION=1.10

RUN set -x \

    # Install packages

    && apk add --no-cache --no-progress --virtual build_deps \
           build-base \
           curl \

    # Install beanstalkd

    && curl -sL "https://github.com/kr/beanstalkd/archive/v$BEANSTALKD_VERSION.tar.gz" | tar fxz - -C /tmp \
    && sed -i "s|#include <sys/fcntl.h>|#include <fcntl.h>|g" /tmp/beanstalkd-$BEANSTALKD_VERSION/sd-daemon.c \
    && make -C /tmp/beanstalkd-$BEANSTALKD_VERSION \
    && make -C /tmp/beanstalkd-$BEANSTALKD_VERSION install PREFIX=/usr \

    # Clean

    && apk del --no-progress \
           build_deps \

    && rm -rf \
           /tmp/*

COPY ./rootfs /

ENTRYPOINT [ "/entrypoint.sh" ]
