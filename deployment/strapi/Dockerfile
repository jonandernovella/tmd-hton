FROM node:18-alpine

ARG UID=1000
ARG GID=1000

RUN	if [ "$UID" -ne 1000 ] || [ "$GID" -ne 1000 ]; then \
	deluser node; \
	addgroup -g "$GID" node; \
	adduser -u "$UID" -G node -s /bin/sh -D node; \
	fi

USER node

WORKDIR /home/node
RUN mkdir app
COPY --chown=node:node ./package.json ./package-lock.json ./

RUN npm ci

WORKDIR /home/node/app
