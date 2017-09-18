FROM ubuntu:latest

LABEL \
    maintainer="Morgan Auchede <morgan.auchede@gmail.com>"

ENV \
    BEANSTALKD_VERSION=latest

RUN set -ex \

    # Prepare system

    && export DEBIAN_FRONTEND=noninteractive \

    && apt-get update \

    # Install packages

    && export BUILD_DEPS="build-essential ca-certificates curl" \

    && apt-get install --no-install-recommends --yes \
           ${BUILD_DEPS} \

    # Install kr/beanstalkd

    && export $(curl "https://raw.githubusercontent.com/timonier/version-lister/release/generated/beanstalkd/${BEANSTALKD_VERSION}" | xargs) \

    && curl --location "https://github.com/kr/beanstalkd/archive/v${BEANSTALKD_VERSION}.tar.gz" | tar --directory /tmp --extract --gzip \
    && make --directory "/tmp/beanstalkd-${BEANSTALKD_VERSION}" \
    && make --directory "/tmp/beanstalkd-${BEANSTALKD_VERSION}" install PREFIX=/usr \

    # Install timonier/dumb-entrypoint

    && curl --location "https://github.com/timonier/dumb-entrypoint/raw/master/src/dumb-entrypoint/installer" | INSTALL_DIRECTORY="/usr/sbin" sh -s -- install \
    && curl --location "https://github.com/timonier/dumb-entrypoint/raw/master/src/dumb-init/installer" | INSTALL_DIRECTORY="/usr/sbin" sh -s -- install \
    && curl --location "https://github.com/timonier/dumb-entrypoint/raw/master/src/gosu/installer" | INSTALL_DIRECTORY="/usr/sbin" sh -s -- install \

    # Clean

    && apt-get remove --purge --yes \
           ${BUILD_DEPS} \
    && apt-get autoremove --purge --yes \

    && rm --force --recursive \
           /tmp/*

ENTRYPOINT [ "dumb-init" , "--" , "dumb-entrypoint" ]
