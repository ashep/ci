FROM --platform=${BUILDPLATFORM} caddy:2-alpine

COPY ./.ci/js/Caddyfile /etc/caddy/Caddyfile
COPY ./build /usr/share/caddy

RUN caddy fmt --overwrite /etc/caddy/Caddyfile
RUN file /usr/bin/caddy
