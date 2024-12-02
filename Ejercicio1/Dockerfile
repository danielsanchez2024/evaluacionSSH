FROM nginx:alpine

RUN rm -f /etc/nginx/conf.d/default.conf

WORKDIR /var/www/html
COPY html/. /var/www/html
RUN chmod 755 /var/www/html

COPY nginx.conf /etx/nginx/conf.d/

COPY ser.key /etc/nginx/
COPY ser.pem /etc/nginx/

COPY nginx.conf /etc/nginx/

EXPOSE 8081 8082

CMD ["nginx", "-g", "daemon off;"]
