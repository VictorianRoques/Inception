FROM debian:buster

RUN apt update -y && apt install -y \
	php7.3-fpm \
	php7.3-mysql \
	wget

#RUN wget -c https://wordpress.org/latest.tar.gz \
	#&& tar -xvzf /latest.tar.gz /usr/src/ \
	#&& rm wordpress.tar.gz

RUN mkdir -p  /var/www/html \
	&& chown -R www-data:www-data /var/www/html/ \
	&& chmod 777 /var/www/html

RUN service php7.3-fpm start

EXPOSE 9000

CMD ["/usr/sbin/php-fpm7.3", "-F"]