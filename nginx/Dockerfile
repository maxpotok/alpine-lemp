FROM alpine:3.13

LABEL MAINTAINER="Maksymilian Potok <makspotok@gmail.com>"
LABEL APP="alemp"

RUN apk update && apk add nginx && \
    adduser -D -g 'www' www && \
    mkdir /www && \
    chown -R www:www /var/lib/nginx && \
    chown -R www:www /www && \
    mkdir -p /run/nginx && \
    chown nginx:nginx /var/lib/nginx/html/* && \
    chmod 777 /var/lib/nginx/


COPY files/index.html /etc/nginx/html/
COPY files/index.html /var/lib/nginx/html/index.html
COPY files/nginx.conf /etc/nginx/nginx.conf

VOLUME ["/var/cache/nginx"]

EXPOSE 80 443

CMD ["nginx"]