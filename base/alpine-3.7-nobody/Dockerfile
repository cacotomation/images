FROM alpine:3.7

ENV PAUSE_CHECKSUM=dd34466cb5e05cf24a819f33a4f30a1e19f84c063fdf023856998ecb068e23c2
ENV GOSU_CHECKSUM=0b843df6d86e270c5b0f5cbd3c326a04e18f4b7f9b8457fa497b0454c4b138d7
ENV TINI_CHECKSUM=c7faf940a2e5234bf9e324861469d7879c44c7152555e8b143f2b7c38c3d2efc

RUN apk add --update --no-cache ca-certificates 

ENV LANG en_US.UTF-8
ENV LANGUAGE en_US:en
ENV LC_ALL en_US.UTF-8
ENV GODEBUG netdns=cgo

# Install pause
RUN set -x \
 && wget https://s3.amazonaws.com/devops-public/pause-amd64 \
 && echo "${PAUSE_CHECKSUM}  pause-amd64" | sha256sum -c - \
 && chmod +x pause-amd64 \
 && mv pause-amd64 /usr/local/bin/pause

# Install gosu
RUN set -x \
 && wget https://github.com/tianon/gosu/releases/download/1.11/gosu-amd64 \
 && echo "${GOSU_CHECKSUM}  gosu-amd64" | sha256sum -c - \
 && chmod +x gosu-amd64 \
 && mv gosu-amd64 /usr/local/bin/gosu

# Install tini
RUN set -x \
 && wget https://github.com/krallin/tini/releases/download/v0.16.1/tini \
 && echo "${TINI_CHECKSUM}  tini" | sha256sum -c - \
 && chmod +x tini \
 && mv tini /usr/local/bin

USER nobody