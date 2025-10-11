FROM golang:trixie AS builder

ARG APP_NAME
ARG APP_VERSION

RUN apt update && apt upgrade -y
COPY . /build
WORKDIR /build
RUN go build -tags osusergo,netgo -ldflags="-extldflags=-static -w -s -X 'main.appName=${APP_NAME}' -X 'github.com/ashep/go-app/runner.appName=$APP_NAME' -X 'main.appVer=$APP_VERSION' -X 'github.com/ashep/go-app/runner.appVer=$APP_VERSION'" -o app.out main.go

FROM alpine:latest
COPY --from=builder /build/app.out /app/app
RUN chmod 0755 /app/app
WORKDIR /app
ENTRYPOINT ["/app/app"]
