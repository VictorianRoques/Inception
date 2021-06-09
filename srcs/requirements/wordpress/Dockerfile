FROM debian:buster

RUN apt update -y && apt install -y \
	php7.3-fpm \
	php7.3-mysql \
	wget

RUN mkdir -p /var/www/html

RUN chown -R www-data:www-data /var/www/html/ \
	&& chmod 777 /var/www/html/

COPY www.conf .
RUN mv www.conf /etc/php/7.3/fpm/pool.d/www.conf
RUN service php7.3-fpm start

EXPOSE 9000

CMD ["/usr/sbin/php-fpm7.3", "-F"]
