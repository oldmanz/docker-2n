ARG APACHE_VERSION=""
FROM httpd:${APACHE_VERSION:+${APACHE_VERSION}-}alpine

RUN apk update; \
    apk upgrade; \
    apk add acl; \
    apk add nano;

# Copy apache vhost file to proxy php requests to php-fpm container
COPY demo.apache.conf /usr/local/apache2/conf/demo.apache.conf
RUN cat /usr/local/apache2/conf/demo.apache.conf >> /usr/local/apache2/conf/httpd.conf

#RUN cd /var/www/html/api \
#  && mkdir bootstrap \
#  && cd bootstrap \
#  && mkdir cache \
#  && setfacl -R -m g:www-data:rwx cache

#RUN touch /var/www/html/api/storage/logs/laravel.log
