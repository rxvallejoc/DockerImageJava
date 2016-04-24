FROM alpine:3.3
MAINTAINER Rodrigo Vallejo <rxvallejoc@gmail.com>

ENV LANG C.UTF-8

RUN { \
  echo '#!/bin/sh'; \
    echo 'set -e'; \
    echo; \
    echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; \
} >   /usr/local/bin/docker-java-home \
  && chmod +x /usr/local/bin/docker-java-homeva-home

ENV JAVA_HOME /usr/lib/jvm/java-1.8-openjdk
ENV PATH $PATH:$JAVA_HOME/bin

ENV JAVA_VERSION 8u77
ENV JAVA_ALPINE_VERSION 8.77.03-r0

RUN set -x \
      && alpinepk add --no-cache \
      openjdk8="$JAVA_ALPINE_VERSION" \
      && [ "$JAVA_HOME" = "$(docker-java-home)" ]
