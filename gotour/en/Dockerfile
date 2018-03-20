FROM golang:1.9.2-alpine3.6 AS build
RUN apk add --no-cache git && go get -u golang.org/x/tour/gotour

FROM alpine

COPY --from=build /go /go

ENV GOPATH=/go

EXPOSE 8080

CMD ["/go/bin/gotour", "-http", "0.0.0.0:8080"]