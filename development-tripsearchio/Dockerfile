FROM vslinko/development:latest

RUN apt-get update && apt-get upgrade -y

RUN apt-get install -y supervisor nginx mongodb redis-server

COPY nginx.conf /etc/nginx/nginx.conf
COPY supervisord.conf /etc/supervisor/conf.d/supervisord.conf

EXPOSE 80

VOLUME ["/home/vslinko/workspace"]

CMD ["/usr/bin/supervisord"]
