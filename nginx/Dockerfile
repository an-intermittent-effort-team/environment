ARG NGINX_VERSION

FROM nginx:${NGINX_VERSION}
USER root
RUN mkdir /var/log/nginx/access  \
    && mkdir /var/log/nginx/error \
    && useradd fixuser -u 1000
