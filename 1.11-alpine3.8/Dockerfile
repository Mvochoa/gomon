FROM golang:1.11-alpine3.8

RUN apk update && apk add git gcc bind-dev musl-dev
RUN go get github.com/githubnemo/CompileDaemon
RUN go install /go/src/github.com/githubnemo/CompileDaemon
RUN chmod +x /go/bin/CompileDaemon
RUN mv /go/bin/CompileDaemon /usr/local/bin/gomon
RUN rm -Rf github.com golang.org

ENV GO111MODULE=on