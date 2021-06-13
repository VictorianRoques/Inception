FROM debian:buster

RUN apt update -y && apt install -y mariadb-server

COPY docker-entrypoint.sh /usr/local/bin/
COPY		my.cnf /etc/mysql/my.cnf

ENTRYPOINT ["docker-entrypoint.sh"]

EXPOSE 3306
