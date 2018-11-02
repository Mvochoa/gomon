FROM golang:1.11.1

RUN go get github.com/githubnemo/CompileDaemon
RUN go install /go/src/github.com/githubnemo/CompileDaemon
RUN chmod +x /go/bin/CompileDaemon
RUN mv /go/bin/CompileDaemon /usr/local/bin/gomon
RUN rm -Rf github.com golang.org