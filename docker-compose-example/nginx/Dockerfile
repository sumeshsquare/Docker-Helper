FROM nginx:1.14.0-alpine

LABEL Jithin Babu "jithinbabusbce@gmail.com"

## Hostname for build
ARG HOSTNAME

## Install open-ssl certificate 
RUN apk add --update openssl && openssl req -x509 -nodes -days 365 -newkey rsa:2048 -keyout /etc/nginx/cert.key -out /etc/nginx/cert.crt -subj "/C=GB/ST=London/L=London/O=Global Security/OU=IT Department/CN=${HOSTNAME}"

COPY nginx.conf.template /etc/nginx/nginx.conf
COPY default /etc/nginx/conf.d/default.template

# forward request and error logs to docker log collector
RUN ln -sf /dev/stdout /var/log/nginx/access.log \
    && ln -sf /dev/stderr /var/log/nginx/error.log

EXPOSE 80
STOPSIGNAL SIGTERM

CMD envsubst '$$HOSTNAME' < /etc/nginx/conf.d/default.template > /etc/nginx/conf.d/node.default.conf \
   && exec nginx -g 'daemon off;'