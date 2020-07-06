
FROM alpine:3.10
LABEL io.buildpacks.stack.id=io.buildpacks.stack.golang.alpine
COPY yj /usr/bin
RUN apk --no-cache add ca-certificates wget
RUN wget -q -O /etc/apk/keys/sgerrand.rsa.pub https://alpine-pkgs.sgerrand.com/sgerrand.rsa.pub
RUN wget https://github.com/sgerrand/alpine-pkg-glibc/releases/download/2.28-r0/glibc-2.28-r0.apk
RUN apk add glibc-2.28-r0.apk
RUN apk update && apk upgrade && apk add --update alpine-sdk && \
    apk add --no-cache bash git openssh make cmake jq gcc
ENV CNB_STACK_ID=io.buildpacks.stack.golang.alpine
ENV CNB_USER_ID=1000
ENV CNB_GROUP_ID=1001
ENV XDG_CACHE_HOME=/tmp/.cache
ARG UID=1000
ARG GID=1001
RUN addgroup -S $GID -g $GID && adduser -S $UID -G $GID -s /bin/sh -h $HOME -u 1000
USER 1000:1001