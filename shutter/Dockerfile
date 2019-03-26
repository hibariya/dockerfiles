# xhost +"local:docker@"
#
# docker run -d --rm \
#   -v /etc/localtime:/etc/localtime:ro \
#   -v /tmp/.X11-unix:/tmp/.X11-unix \
#   -v "${HOME}/.config/autostart:${HOME}/.config/autostart" \
#   -v "${HOME}/Pictures:${HOME}/Pictures" \
#   -v "${HOME}/.shutter/settings.xml:${HOME}/.shutter/settings.xml" \
#   -e "HOME=${HOME}" \
#   -e "DISPLAY=unix${DISPLAY}" \
#   --name shutter \
#   hibariya/shutter "$@"


FROM debian:stretch

LABEL maintainer "hibariya@gmail.com"

RUN apt-get update \
    && apt-get install -y --no-install-recommends \
      shutter libgoo-canvas-perl \
    && rm -rf /var/lib/apt/lists/*
RUN mkdir -p /root/Pictures /root/.shutter /root/.config/autostart

WORKDIR /root/Pictures
ENTRYPOINT [ "shutter" ]
