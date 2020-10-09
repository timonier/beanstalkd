FROM debian:stable-slim

LABEL \
    maintainer="Morgan AUCHEDE <morgan.auchede@gmail.com>"

ENV \
    LC_ALL=C.UTF-8

RUN set -e -u -x \
\
    # Prepare system
\
    && export DEBIAN_FRONTEND=noninteractive \
    && apt-get update \
\
    # Install packages
\
    && BUILD_DEPS="build-essential curl" \
    && apt-get install --no-install-recommends --yes ${BUILD_DEPS} ca-certificates locales \
\
    # Install beanstalkd
\
    && curl --location "https://github.com/beanstalkd/beanstalkd/archive/v1.12.tar.gz" | tar --directory /tmp --extract --gzip \
    && make --directory /tmp/beanstalkd-1.12 \
    && make --directory /tmp/beanstalkd-1.12 install \
\
    # Clean
\
    && apt-get remove --purge --yes ${BUILD_DEPS} \
    && apt-get autoremove --purge --yes \
    && rm -f -r /tmp/* /var/lib/apt/lists/*
