FROM ubuntu:14.10
MAINTAINER Bert Chang "https://github.com/lazywei"

# We use bash
RUN rm /bin/sh && ln -s /bin/bash /bin/sh

RUN apt-get update
RUN apt-get install -y git curl zlib1g-dev build-essential libssl-dev libreadline-dev libyaml-dev libsqlite3-dev sqlite3 libxml2-dev libxslt1-dev libcurl4-openssl-dev python-software-properties autoconf ruby bison

RUN git clone https://github.com/sstephenson/rbenv.git /root/.rbenv
RUN git clone https://github.com/sstephenson/ruby-build.git /root/.rbenv/plugins/ruby-build
RUN /root/.rbenv/plugins/ruby-build/install.sh
ENV PATH /root/.rbenv/bin:$PATH
RUN echo 'eval "$(rbenv init -)"' >> /etc/profile.d/rbenv.sh # or /etc/profile
RUN echo 'eval "$(rbenv init -)"' >> .bashrc

ENV CONFIGURE_OPTS --disable-install-doc

RUN rbenv install 2.1.3
RUN rbenv global 2.1.3

RUN echo 'gem: --no-rdoc --no-ri' >> /.gemrc
RUN gem install bundler

RUN mkdir -p /src
