# TODO: use an appropriate seccomp profile instead of running with `--privileged`.
# Example:
#   xhost +"local:docker@"
#   docker run --rm -d \
#     -v /tmp/.X11-unix:/tmp/.X11-unix \
#     -v /dev/shm:/dev/shm \
#     -v "${HOME}/Dropbox:/Dropbox" \
#     -v "${HOME}/.config/pulse/cookie:/root/.config/pulse/cookie" \
#     -v "/run/user/${UID}/pulse/native:/run/pulse/native" \
#     -e PULSE_SERVER=unix:/run/pulse/native \
#     -e PULSE_COOKIE=/root/.config/pulse/cookie \
#     -e DISPLAY=unix$DISPLAY \
#     --device /dev/snd \
#     --group-add $(getent group audio | cut -d: -f3) \
#     --group-add $(getent group video | cut -d: -f3) \
#     --name audacity \
#     --privileged --userns host \
#     hibariya/audacity "$@"

FROM debian:sid
LABEL maintainer "hibariya@gmail.com"

RUN apt-get update \
    && apt-get install -yq --no-install-recommends audacity pulseaudio \
    && rm -rf /var/lib/apt/lists/*

ENTRYPOINT ["audacity"]
