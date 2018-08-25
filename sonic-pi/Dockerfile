# TODO: use an appropriate seccomp profile instead of running with `--privileged`.
# Example:
#   xhost +"local:docker@"
#   docker run -d --rm \
#     -v /tmp/.X11-unix:/tmp/.X11-unix \
#     -v /dev/shm:/dev/shm \
#     -v "${HOME}/Dropbox/sonic-pi:/sonic-pi" \
#     -v "${HOME}/.config/pulse/cookie:/root/.config/pulse/cookie" \
#     -v "/run/user/${UID}/pulse/native:/run/pulse/native" \
#     -e PULSE_SERVER=unix:/run/pulse/native \
#     -e PULSE_COOKIE=/root/.config/pulse/cookie \
#     -e DISPLAY=unix$DISPLAY \
#     -e JACK_NO_AUDIO_RESERVATION=1 \
#     --device /dev/snd \
#     --group-add $(getent group audio | cut -d: -f3) \
#     --group-add $(getent group video | cut -d: -f3) \
#     --publish 4556-4562:4556-4562 \
#     --privileged --userns host \
#     --name sonic-pi \
#     hibariya/sonic-pi "$@"

FROM debian:sid
LABEL maintainer "hibariya@gmail.com"

ENV DEBIAN_FRONTEND=noninteractive

COPY audio.conf /etc/security/limits.d/audio.conf
RUN apt-get update \
    && apt-get install -yq --no-install-recommends sonic-pi pulseaudio \
    && rm -rf /var/lib/apt/lists/*

EXPOSE 4556-4562

ENTRYPOINT ["sonic-pi"]
