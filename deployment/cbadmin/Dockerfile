FROM node:16-alpine AS bundler

RUN apk add --no-cache git

USER node

WORKDIR /home/node/

ARG CHARTBREW_TAG=v2.6.2
RUN git -C . clone --depth 1 --branch $CHARTBREW_TAG https://github.com/chartbrew/chartbrew

WORKDIR /home/node/chartbrew/client

RUN npm install

ARG REACT_APP_CLIENT_HOST
ENV REACT_APP_CLIENT_HOST=${REACT_APP_CLIENT_HOST}

ARG REACT_APP_API_HOST
ENV REACT_APP_API_HOST=${REACT_APP_API_HOST}

RUN npm run build

FROM nginx:1-alpine-slim

RUN mkdir -p /app/dist
COPY --from=bundler /home/node/chartbrew/client/build /app/dist
