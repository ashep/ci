FROM alpine:latest
COPY app.out /app/app
RUN chmod 0755 /app/app
WORKDIR /app
ENTRYPOINT ["/app/app"]
