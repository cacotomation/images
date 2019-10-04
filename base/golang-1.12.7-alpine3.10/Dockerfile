FROM golang:1.12.7-alpine3.10

ENV LANG en_US.UTF-8
ENV LANGUAGE en_US:en
ENV LC_ALL en_US.UTF-8
ENV GODEBUG netdns=cgo

RUN apk add --update --no-cache ca-certificates
RUN set -x && update-ca-certificates

USER nobody