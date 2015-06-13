FROM vslinko/development:latest

ENV DEBIAN_FRONTEND noninteractive

RUN apt-get update && apt-get upgrade -y

RUN apt-get install -y supervisor memcached p7zip imagemagick mysql-server\
 postgresql-server-dev-9.3 libmysqlclient-dev nginx

COPY supervisord.conf /etc/supervisor/conf.d/supervisord.conf
COPY nginx.conf /etc/nginx/nginx.conf

EXPOSE 80

VOLUME ["/home/vslinko/workspace"]

CMD ["/usr/bin/supervisord"]
