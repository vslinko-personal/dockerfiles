FROM vslinko/development:latest

ENV DEBIAN_FRONTEND noninteractive

RUN apt-get update && apt-get upgrade -y

RUN apt-get install -y supervisor mysql-server php5-fpm nginx

COPY php-fpm.conf /etc/php5/fpm/php-fpm.conf
COPY nginx.conf /etc/nginx/nginx.conf
COPY supervisord.conf /etc/supervisor/conf.d/supervisord.conf
COPY app_dev.php /home/vslinko/workspace/web/app_dev.php

EXPOSE 80

VOLUME ["/home/vslinko/workspace"]

CMD ["/usr/bin/supervisord"]
