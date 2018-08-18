# Example:
#   xhost +"local:docker@"
#   docker run -d --rm \
#     -v /tmp/.X11-unix:/tmp/.X11-unix \
#     -v /dev/shm:/dev/shm \
#     -v "${HOME}/Dropbox/lmms:/lmms" \
#     -e DISPLAY=unix$DISPLAY \
#     --device /dev/snd \
#     --group-add $(getent group audio | cut -d: -f3) \
#     --name lmms \
#     hibariya/lmms "$@"

FROM debian:sid
LABEL maintainer "hibariya@gmail.com"

RUN apt-get update \
    && apt-get install -yq lmms \
    && rm -rf /var/lib/apt/lists/*

ENTRYPOINT ["lmms"]
