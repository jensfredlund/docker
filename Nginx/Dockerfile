FROM alpine:3.8

EXPOSE 443

RUN apk add --no-cache nginx groff less python py-pip && \
    mkdir /app && \
    mkdir /etc/nginx/certs && \
    mkdir -p /run/nginx && \
    pip install awscli && \
    apk -v --purge del py-pip

COPY files/certs/ /etc/nginx/certs/
COPY files/nginx/default.conf /etc/nginx/conf.d/default.conf
COPY files/www/index.html /var/www/index.html
COPY files/scripts/docker-entrypoint.sh /app/

ENTRYPOINT ["./app/docker-entrypoint.sh"]
