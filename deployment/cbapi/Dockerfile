FROM node:16-alpine AS bundler

RUN apk add --no-cache git

USER node

WORKDIR /home/node/

ARG CHARTBREW_TAG=v2.6.2
RUN git -C . clone --depth 1 --branch $CHARTBREW_TAG https://github.com/chartbrew/chartbrew

WORKDIR /home/node/chartbrew/server

RUN npm install
