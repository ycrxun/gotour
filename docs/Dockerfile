FROM golang:1.9-alpine AS build
RUN apk add --no-cache git && \
go get github.com/golang-china/golangdoc && \
git clone --depth=1 https://github.com/golang-china/golangdoc.translations /user/local/go/translations

FROM alpine

COPY --from=build /go /go
COPY --from=build /user/local/go /user/local/go

ENV GOPATH=/go
ENV GOROOT=/user/local/go

EXPOSE 8080

CMD [ "/go/bin/golangdoc", "-http=:8080", "-lang=zh_CN" ]