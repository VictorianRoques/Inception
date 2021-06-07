FROM debian:buster

RUN apt update -y && apt install -y \
	wordpress

COPY ./wordpress /wordpress

EXPOSE 9000

# CMD ["php",  "-S", "0.0.0.0:9000" , "-t" ,"/wordpress"]
CMD bash
