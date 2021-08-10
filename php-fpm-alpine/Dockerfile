FROM php:7.4-fpm-alpine3.14

RUN set -eux; \
    apk add --no-cache openldap-dev \
      libldap \
      runc && \
    docker-php-ext-install ldap && \
    docker-php-ext-configure ldap && \
    # cleanup \
    apk del \
      gcc \
      g++ \
      .phpize-deps-configure
