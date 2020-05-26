FROM haproxy:1.8.25-alpine
LABEL maintainer="<wxxx333@gmail.com>"

ARG BUILD_DATE
ARG VCS_REF
ARG VERSION

LABEL architecture="x86_64"               \
      build-date="$BUILD_DATE"            \
      license="MIT"                       \
      name="bugre/haproxy"               \
      summary="Simple HaProxy Container/Docker, configurable via environment variables"   \
      version="$VERSION"                  \
      vcs-ref="$VCS_REF"                  \
      vcs-type="git"                      \
      vcs-url="https://github.com/bugre/haproxy-container"

RUN apk add --update --no-cache ca-certificates python3 rsyslog bash     \
 && ln -s /usr/local/etc/haproxy /etc/haproxy                            \
 && mv /docker-entrypoint.sh /haproxy-entrypoint.sh

COPY /src/haproxy.cfg  /tmp
COPY /src/rsyslog.conf /etc
COPY /src/*  /