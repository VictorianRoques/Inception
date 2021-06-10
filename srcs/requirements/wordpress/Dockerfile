FROM debian:buster

RUN apt update -y && apt install -y \
	php7.3-fpm \
	php7.3-mysql \
	wget

RUN mkdir -p /var/www/html

RUN echo "listen = 9000" >> /etc/php/7.3/fpm/pool.d/www.conf

RUN service php7.3-fpm start

EXPOSE 9000

CMD ["/usr/sbin/php-fpm7.3", "-F"]
