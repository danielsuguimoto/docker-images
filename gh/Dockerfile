FROM alpine/git

LABEL maintainer="Daniel Jun Suguimoto <danielsuguimoto@gmail.com>"

RUN apk --update add git less openssh && \
    rm -rf /var/lib/apt/lists/* && \
    rm /var/cache/apk/*

RUN apk add gh --repository=https://cli.github.com/packages

ENTRYPOINT ["gh"]
CMD ["--help"]