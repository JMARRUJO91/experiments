FROM golang:alpine as builder

WORKDIR /go/src
COPY httpserver.go .

RUN go build -o myhttpserver ./httpserver.go


From alpine:3.20.3

WORKDIR /root/
COPY --from=builder /go/src/myhttpserver .
RUN chmod +x /root/myhttpserver

ENTRYPOINT ["/root/myhttpserver"]
