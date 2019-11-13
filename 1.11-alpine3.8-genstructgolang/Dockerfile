FROM golang:1.11-alpine3.8

RUN apk update && apk add git gcc bind-dev musl-dev
RUN go get github.com/mvochoa/CompileDaemon && \
    go get gitlab.com/watud/genstructgraphql
RUN go install /go/src/github.com/mvochoa/CompileDaemon && \
    go install /go/src/gitlab.com/watud/genstructgraphql
RUN chmod +x /go/bin/CompileDaemon && \
    chmod +x /go/bin/genstructgraphql
RUN mv /go/bin/CompileDaemon /usr/local/bin/gomon && \
    mv /go/bin/genstructgraphql /usr/local/bin/genstructgraphql
RUN rm -Rf github.com golang.org gitlab.com

ENV GO111MODULE=on

COPY docker-entrypoint.sh /usr/local/bin/
COPY genstruct.sh /usr/local/bin/genstruct
ENTRYPOINT ["sh", "/usr/local/bin/docker-entrypoint.sh"]