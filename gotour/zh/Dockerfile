FROM golang:1.9.2-alpine3.6 AS build
RUN apk add --no-cache git && go get -u github.com/Go-zh/tour/gotour

FROM alpine

COPY --from=build /usr/local/bin/gotour /usr/local/bin/gotour

EXPOSE 8080

CMD ["/usr/local/bin/gotour", "-http", "0.0.0.0:8080"]