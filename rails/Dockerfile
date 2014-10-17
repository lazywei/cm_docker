FROM lazywei/cm_base:latest
MAINTAINER Bert Chang "https://github.com/lazywei"

RUN apt-get install -y nodejs npm
RUN apt-get install -y memcached

VOLUME ["/root/src/codementor"]

CMD memcached -d && bash
