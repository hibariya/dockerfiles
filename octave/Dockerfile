# xhost +"local:docker@"
#
# docker run -d --rm \
#   -v /etc/localtime:/etc/localtime:ro \
#   -v /tmp/.X11-unix:/tmp/.X11-unix \
#   -v ~/.config/octave:/root/.config/octave \
#   -v "$(pwd):/app" \
#   -e "DISPLAY=unix${DISPLAY}" \
#   --name octave \
#   hibariya/octave "$@"

FROM debian:buster

LABEL maintainer "hibariya@gmail.com"

RUN apt update \
    && apt install -y --no-install-recommends \
      octave libqt5sql5-sqlite fonts-freefont-otf fonts-noto-cjk \
    && rm -rf /var/lib/apt/lists/*

ENV LC_ALL=C.UTF-8
ENTRYPOINT [ "octave", "--gui" ]
