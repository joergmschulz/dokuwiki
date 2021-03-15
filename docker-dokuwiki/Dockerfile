# FROM nginxinc/nginx-unprivileged:alpine
FROM nginx:stable-alpine
LABEL maintainer js@jslz.de

#ARG NGINX_GID
#ARG NGINX_GROUP
#ARG NGINX_UID
#ARG NGINX_USER

#RUN    addgroup -S -g ${NGINX_GID} ${NGINX_GROUP} || export NGINX_GROUP=www-data  && \
#       adduser -S -D -H -u $NGINX_UID -G $NGINX_GROUP -g "WWW nginx" ${NGINX_USER} && \
#    \
#RUN    set -x && \
#    apk update && \
#    apk upgrade && \
#    apk add --no-cache \
#      curl && \
RUN cd /usr/share/nginx/html && \
    curl -O https://download.dokuwiki.org/src/dokuwiki/dokuwiki-stable.tgz && \
    tar -xzvf dokuwiki-stable.tgz --strip-components=1 -C /usr/share/nginx/html
    #&& cd /var/www/html \
    #&& find . -type d -exec chmod 755 {} \; \
    #&& find . -type f -exec chmod 644 {} \; \
    #&& chown -R ${NGINX_USER}:${NGINX_GROUP} .

EXPOSE	80
#COPY entrypoint.sh /usr/local/bin/entrypoint.sh
#RUN chmod +x /usr/local/bin/entrypoint.sh
#USER $NGINX_USER
#ENTRYPOINT ["/usr/local/bin/entrypoint.sh"]
