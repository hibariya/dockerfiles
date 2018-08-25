# Example:
#   xhost +"local:docker@"
#   docker run -d --rm \
#     -v /tmp/.X11-unix:/tmp/.X11-unix \
#     -v /dev/shm:/dev/shm \
#     -v "${HOME}/Dropbox/lmms:/root/lmms" \
#     -v "${HOME}/.config/pulse/cookie:/root/.config/pulse/cookie" \
#     -v "/run/user/${UID}/pulse/native:/run/pulse/native" \
#     -e PULSE_SERVER=unix:/run/pulse/native \
#     -e PULSE_COOKIE=/root/.config/pulse/cookie \
#     -e DISPLAY=unix$DISPLAY \
#     --device /dev/snd \
#     --group-add $(getent group audio | cut -d: -f3) \
#     --name lmms \
#     hibariya/lmms "$@"

FROM debian:sid
LABEL maintainer "hibariya@gmail.com"

RUN apt-get update \
    && apt-get install -yq --no-install-recommends lmms pulseaudio \
    && rm -rf /var/lib/apt/lists/*

ENTRYPOINT ["lmms"]
