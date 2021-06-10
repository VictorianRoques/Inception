FROM debian:buster

RUN apt update && apt install -y mariadb-server

#need to create mariadb user

EXPOSE 3306

CMD ["mysqld"]