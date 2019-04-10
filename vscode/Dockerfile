# Example:
#   xhost +"local:docker@"
#   docker run -d --rm \
#     -v /etc/localtime:/etc/localtime:ro \
#     -v /tmp/.X11-unix:/tmp/.X11-unix  \
#     -v $HOME/src:/root/src \
#     -v $HOME/.config/Code:/root/.config/Code \
#     -v $HOME/.vscode:/root/.vscode \
#     -e "DISPLAY=unix${DISPLAY}" \
#     -e "HOME=/root" \
#     --device /dev/dri \
#     --name visualstudio \
#     hibariya/vscode /usr/share/code/code

FROM r.j3ss.co/vscode
LABEL maintainer "hibariya@gmail.com"

RUN apt-get update \
    && apt-get install -yq --no-install-recommends \
    fonts-noto-cjk \
    ruby ruby-dev \
    && rm -rf /var/lib/apt/lists/*
