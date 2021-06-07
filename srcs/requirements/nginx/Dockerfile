FROM debian:buster

RUN apt update && apt install -y \
	nginx \
	openssl

RUN mkdir -p /var/www/viroques
COPY viroques.conf . 
COPY index.html /var/www/viroques

RUN mv viroques.conf /etc/nginx/sites-available/ \
	&& rm /etc/nginx/sites-enabled/default \
	&& ln -s /etc/nginx/sites-available/viroques.conf /etc/nginx/sites-enabled/

RUN openssl req -x509 -nodes -days 365 -newkey rsa:2048 -keyout /etc/ssl/private/viroques.key -out /etc/ssl/certs/viroques.crt -subj "/C=FR/ST=Ile de France/L=Paris/O=Ecole 42/OU=Ecole 42/CN=viroques"

RUN chown -R www-data:www-data /var/www/* \
	&& chmod -R 755 /var/www/*

EXPOSE 443

CMD ["nginx", "-g", "daemon off;"]
