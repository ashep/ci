FROM --platform=${BUILDPLATFORM} caddy:2-alpine AS builder
COPY ./.ci/js/Caddyfile /etc/caddy/Caddyfile
RUN caddy fmt --overwrite /etc/caddy/Caddyfile

FROM --platform=${TARGETPLATFORM} caddy:2-alpine
COPY --from=builder /etc/caddy/Caddyfile /etc/caddy/Caddyfile
COPY ./build /usr/share/caddy
