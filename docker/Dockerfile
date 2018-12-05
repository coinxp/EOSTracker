FROM ubuntu:16.04

RUN apt-get update \
    && apt-get install curl -y \
    && curl -sL https://deb.nodesource.com/setup_8.x |  bash - \
    && apt-get install nodejs -y

RUN mkdir -p /usr/src/app

WORKDIR /usr/src/app

COPY ./ /usr/src/app

RUN npm install \
    && node patch.js \
    && npm install -g @angular/cli

EXPOSE 4200

ENTRYPOINT [ "npm","run","start" ]
