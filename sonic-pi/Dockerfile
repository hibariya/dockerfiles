# TODO: use an appropriate seccomp profile instead of running with `--privileged`.
# Example:
#   xhost +"local:docker@"
#   docker run -d --rm \
#     -v /tmp/.X11-unix:/tmp/.X11-unix \
#     -v /dev/shm:/dev/shm \
#     -v "${HOME}/Dropbox/sonic-pi:/sonic-pi" \
#     -e DISPLAY=unix$DISPLAY \
#     -e JACK_NO_AUDIO_RESERVATION=1 \
#     --device /dev/snd \
#     --device /dev/dri \
#     --device /dev/video0 \
#     --group-add $(getent group audio | cut -d: -f3) \
#     --group-add $(getent group video | cut -d: -f3) \
#     --publish 4556-4562:4556-4562 \
#     --privileged --userns host \
#     hibariya/sonic-pi "$@"

FROM debian:sid
LABEL maintainer "hibariya@gmail.com"

ENV DEBIAN_FRONTEND=noninteractive

COPY audio.conf /etc/security/limits.d/audio.conf
RUN apt-get update \
    && apt-get install -yq sonic-pi \
    && rm -rf /var/lib/apt/lists/*

EXPOSE 4556-4562

ENTRYPOINT [ "sonic-pi" ]
