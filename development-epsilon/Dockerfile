FROM vslinko/development-symfony:latest

ENV DEBIAN_FRONTEND noninteractive

RUN apt-get update && apt-get upgrade -y

RUN apt-get install -y memcached redis-server

COPY supervisord.conf /etc/supervisor/conf.d/supervisord.conf

EXPOSE 80

VOLUME ["/home/vslinko/workspace"]

CMD ["/usr/bin/supervisord"]
