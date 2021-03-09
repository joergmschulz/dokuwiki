FROM php:7.4-alpine

LABEL maintainer js@jslz.de


RUN    addgroup -S -g ${NGINX_GID} nginx || export NGINX_GROUP=www-data  && adduser -S -D -H -u $NGINX_UID -G $NGINX_GROUP -g "WWW nginx" ${NGINX_USER} && \
    \
    set -x && \
    apk update && \
    apk upgrade && \
    apk add --no-cache \
      curl && \
    curl -O https://download.dokuwiki.org/src/dokuwiki/dokuwiki-stable.tgz && \
    tar -xzvf dokuwiki-stable.tgz --strip-components=1 -C /var/www/html \
    && cd /var/www/html \
    && find . -type d -exec chmod 755 {} \; \
    && find . -type f -exec chmod 644 {} \; \
    && chown -R NGINX_USER:NGINX_GROUP .

COPY entrypoint.sh /usr/local/bin/entrypoint.sh
RUN chmod +x /usr/local/bin/entrypoint.sh
USER $NGINX_USER
ENTRYPOINT ["/usr/local/bin/entrypoint.sh"]
