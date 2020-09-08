FROM alpine/git

LABEL maintainer="Daniel Jun Suguimoto <danielsuguimoto@gmail.com>"

RUN wget -O gh.tgz  --progress=dot:mega https://github.com/cli/cli/releases/download/v0.12.0/gh_0.12.0_linux_amd64.tar.gz && \
    mkdir /gh && \
    tar -xvf gh.tgz -C /gh --strip-components 1

VOLUME /git
WORKDIR /git

ENTRYPOINT ["gh"]
CMD ["--help"]