FROM alpine:3.20

RUN apk add --no-cache nginx
#RUN sed -i '19i daemon off;' /etc/nginx/nginx.conf
RUN mkdir -p /var/www/website
RUN rm /etc/nginx/http.d/default.conf

WORKDIR /var/www/website

COPY config/nginx-site.conf /etc/nginx/http.d
COPY config/index.html .
COPY config/smile-istock.jpg .

RUN chown -R root:www-data .

EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]
