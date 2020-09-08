FROM alpine/git

LABEL maintainer="Daniel Jun Suguimoto <danielsuguimoto@gmail.com>"

RUN apk add gh --update-cache --repository https://cli.github.com/packages

VOLUME /git
WORKDIR /git

ENTRYPOINT ["gh"]
CMD ["--help"]