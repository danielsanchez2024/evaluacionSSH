FROM nginx:alpine

RUN apk add --no-cache openssl

RUN mkdir -p /etc/nginx/certs

RUN openssl req -x509 -nodes -days 365 -newkey rsa:4096 -keyout /etc/nginx/certs/blog.midominio.local.key -out /etc/nginx/certs/blog.midominio.local.crt -subj "/CN=blog.midominio.local"
RUN openssl req -x509 -nodes -days 365 -newkey rsa:4096 -keyout /etc/nginx/certs/app.midominio.local.key -out /etc/nginx/certs/app.midominio.local.crt -subj "/CN=app.midominio.local"

COPY nginx.conf /etc/nginx/nginx.conf


EXPOSE 80 443

