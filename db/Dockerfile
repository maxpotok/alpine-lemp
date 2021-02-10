FROM alpine:3.13

LABEL MAINTAINER="Maksymilian Potok <makspotok@gmail.com>"
LABEL APP="alemp"

#ENV TZ=Europe/Warsaw
#ENV MYSQL_ROOT_PASSWORD=root
#ENV MYSQL_DATABASE=test
#ENV MYSQL_USER=foo
#ENV MYSQL_PASSWORD=bar

WORKDIR /app
VOLUME /app

RUN apk update && apk add bash mysql mysql-client && rm -f /var/cache/apk/*

COPY db/setup.sh /setup.sh
COPY db/my.cnf /etc/mysql/my.cnf

EXPOSE 3306

CMD ["/setup.sh"]
