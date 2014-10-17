FROM lazywei/cm_psql:latest
MAINTAINER Bert Chang "https://github.com/lazywei"

RUN apt-get install -y nodejs npm
RUN apt-get install -y memcached

RUN cd /root/src &&\
        wget http://download.redis.io/releases/redis-2.8.17.tar.gz &&\
        tar xvfz redis-2.8.17.tar.gz &&\
        cd redis-2.8.17 &&\
        make && make install

CMD memcached -d &&\
        redis-server & bash
