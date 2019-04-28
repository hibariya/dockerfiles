# xhost +"local:docker@"
#
# docker run -d --rm \
#   -v /etc/localtime:/etc/localtime:ro \
#   -v /tmp/.X11-unix:/tmp/.X11-unix \
#   -v "${HOME}/.local/share:/root/.local/share" \
#   -e "DISPLAY=unix${DISPLAY}" \
#   --name anki \
#   hibariya/anki "$@"

FROM debian:buster

LABEL maintainer "hibariya@gmail.com"

RUN apt-get update \
    && apt-get install -y --no-install-recommends \
      anki fonts-noto-cjk \
    && rm -rf /var/lib/apt/lists/*

ENV LC_ALL=C.UTF-8 QTWEBENGINE_DISABLE_SANDBOX=1
ENTRYPOINT [ "anki" ]
