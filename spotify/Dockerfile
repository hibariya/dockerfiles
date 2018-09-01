# Example:
#   xhost +"local:docker@"
#   docker run -d --rm \
#     --device /dev/snd \
#     -v /etc/localtime:/etc/localtime:ro \
#     -v /tmp/.X11-unix:/tmp/.X11-unix \
#     -v $HOME/.spotify/config:/home/spotify/.config/spotify \
#     -v $HOME/.spotify/cache:/home/spotify/spotify \
#     -v "${HOME}/.config/pulse/cookie:/root/.config/pulse/cookie" \
#     -v "/run/user/${UID}/pulse/native:/run/pulse/native" \
#     -e PULSE_SERVER=unix:/run/pulse/native \
#     -e PULSE_COOKIE=/root/.config/pulse/cookie \
#     -e DISPLAY=unix$DISPLAY \
#     --user 0 \
#     --group-add $(getent group audio | cut -d: -f3) \
#     --privileged --userns host \
#     --name spotify \
#     hibariya/spotify "$@"

FROM jess/spotify
LABEL maintainer "hibariya@gmail.com"

USER root
RUN apt-get update \
    && apt-get install -yq --no-install-recommends pulseaudio fonts-noto-cjk \
    && rm -rf /var/lib/apt/lists/*
