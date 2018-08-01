# xhost +"local:docker@"
#
# docker run -d --rm \
#   -v /etc/localtime:/etc/localtime:ro \
#   -v /tmp/.X11-unix:/tmp/.X11-unix \
#   -v "${HOME}/Pictures:/root/Pictures" \
#   -v "${HOME}/.shutter/settings.xml:/root/.shutter/settings.xml" \
#   -e "DISPLAY=unix${DISPLAY}" \
#   --name shutter \
#   hibariya/shutter "$@"

FROM debian:stretch

LABEL maintainer "hibariya@gmail.com"

RUN apt-get update \
    && apt-get install -y --no-install-recommends shutter \
    && rm -rf /var/lib/apt/lists/*
RUN mkdir -p /root/Pictures /root/.shutter /root/.config/autostart

WORKDIR /root/Pictures
ENTRYPOINT [ "shutter" ]
