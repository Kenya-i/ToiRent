FROM node:16-alpine as node
FROM nginx:1.18-alpine

ENV TZ=UTC

RUN apk update && \
  apk add --update --no-cache --virtual=.build-dependencies g++

COPY --from=node /usr/local/bin /usr/local/bin

COPY --from=node /usr/local/lib /usr/local/lib

COPY ./docker/nginx/*.conf /etc/nginx/conf.d/

WORKDIR /var/www/html
