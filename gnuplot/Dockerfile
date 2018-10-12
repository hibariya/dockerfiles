# xhost +"local:docker@"
# docker run -it --rm \
#   -v /etc/localtime:/etc/localtime:ro \
#   -v /tmp/.X11-unix:/tmp/.X11-unix \
#   -v "$(pwd):/root" \
#   -e "DISPLAY=unix${DISPLAY}" \
#   --name gnuplot \
#   --privileged --userns host \
#   hibariya/gnuplot "$@"

FROM debian:buster-slim

LABEL maintainer "hibariya@gmail.com"

RUN apt-get update \
    && apt-get install -y --no-install-recommends gnuplot \
    && rm -rf /var/lib/apt/lists/*

WORKDIR /root
ENTRYPOINT [ "gnuplot" ]
