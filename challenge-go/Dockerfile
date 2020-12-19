FROM golang:alpine3.12 as golang

WORKDIR /go/src/index

COPY index.go /go/src/index

ENV CGO_ENABLED=0

RUN go build  -ldflags '-w -s' -a -installsuffix cgo -o /go/bin/index

FROM scratch

COPY --from=golang /go/bin/index /index

CMD ["/index"]
