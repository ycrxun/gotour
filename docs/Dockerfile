FROM golang:1.9

RUN apk add --no-cache git && \
go get github.com/golang-china/golangdoc && \
git clone --depth=1 https://github.com/golang-china/golangdoc.translations /usr/local/go/translations

EXPOSE 6060

CMD [ "/go/bin/golangdoc", "-http=:6060", "-lang=zh_CN" ]
