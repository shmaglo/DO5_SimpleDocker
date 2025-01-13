FROM nginx
WORKDIR /home/

COPY ./nginx/nginx.conf /etc/nginx/nginx.conf
COPY ./server/server.c  .
COPY ./run.sh  .

RUN \
    apt-get update && apt-get install -y gcc spawn-fcgi libfcgi-dev && \
    rm -rf /var/lib/apt/lists && \
    useradd -m -s /bin/bash nonrootuser

USER nonrootuser

ENTRYPOINT ["sh", "./run.sh"]