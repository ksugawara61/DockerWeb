FROM nginx:latest

#RUN cp /usr/share/zoneinfo/Asia/Tokyo /etc/localtime

COPY ./assets/nginx/ssl  /etc/nginx/ssl
COPY ./assets/nginx/nginx.conf  /etc/nginx/nginx.conf
COPY ./assets/nginx/conf.d/  /etc/nginx/conf.d/

COPY ./app /var/www/html/web

WORKDIR /var/log/nginx
RUN mkdir default web

VOLUME /var/log/nginx/default
VOLUME /var/log/nginx/web
