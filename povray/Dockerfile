# xhost +"local:docker@"
#
# docker run -it --rm \
#   -v /etc/localtime:/etc/localtime:ro \
#   -v /tmp/.X11-unix:/tmp/.X11-unix \
#   -v "$(pwd):/root" \
#   -e "DISPLAY=unix${DISPLAY}" \
#   --name povray \
#   hibariya/povray "$@"

FROM debian:buster

LABEL maintainer "hibariya@gmail.com"

RUN apt-get update \
    && apt-get install -y --no-install-recommends povray povray-includes \
    && rm -rf /var/lib/apt/lists/*

RUN echo "Pause_When_Done=true" >> /etc/povray/3.7/povray.ini

WORKDIR /root
ENTRYPOINT [ "povray" ]
