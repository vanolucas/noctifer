FROM php:8.1-alpine

STOPSIGNAL SIGINT

RUN addgroup -S www \
&& adduser -S -G www www \
&& mkdir -p /tmp/html \
&& mkdir -p /var/www/

# clone Noctifer-Music from github
RUN set -x \
&& apk add --no-cache git \
&& git clone https://github.com/lrkrol/Noctifer-Music.git /tmp/html \
&& apk del --no-network git

# move Noctifer-Music to PHP web server html dir
RUN cp -r /tmp/html /var/www/ \
&& mkdir -p /var/www/html/music \
&& chown -R www:www /var/www/html

WORKDIR /var/www/html

USER www

ENTRYPOINT [ "docker-php-entrypoint" ]

CMD [ "php", "-S", "[::]:8080", "-t", "/var/www/html" ]

EXPOSE 8080