# mkdir -p "${HOME}/.local/share/heroku"
# docker run --rm -it \
#   -v /etc/localtime:/etc/localtime:ro \
#   -v "${HOME}/.local/share/heroku:/root/.local/share/heroku" \
#   -v "${HOME}/.netrc:/root/.netrc" \
#   -v "$(pwd):/app" \
#   --name heroku \
#   hibariya/heroku "$@"

FROM node:latest

LABEL maintainer "hibariya@gmail.com"

RUN curl https://cli-assets.heroku.com/install-ubuntu.sh | sh && rm -rf /var/lib/apt/lists/*
RUN mkdir -p /root/.local/share/heroku /app

WORKDIR /app
ENTRYPOINT ["heroku"]
