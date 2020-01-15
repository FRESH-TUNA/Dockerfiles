FROM amazonlinux

ENV RUBY_VERSION 2.6.3
ENV RUBY_INSTALL_PACKAGE 0.7.0

# update packages and install required packages
RUN yum update -y && yum clean all \
    && yum install -y which tar gzip procps \
    patch libyaml-devel libffi-devel glibc-headers autoconf \
    gcc-c++ glibc-devel readline-devel zlib-devel openssl-devel \
    bzip2 automake libtool bison \
    wget git mysql-devel make libcurl-devel crontabs && yum clean all

#ruby install
WORKDIR /ruby-install
RUN wget -O ruby-install-${RUBY_INSTALL_PACKAGE}.tar.gz https://github.com/postmodern/ruby-install/archive/v${RUBY_INSTALL_PACKAGE}.tar.gz \
    && tar -xzvf ruby-install-${RUBY_INSTALL_PACKAGE}.tar.gz \
    && cd /ruby-install/ruby-install-${RUBY_INSTALL_PACKAGE}/ \
    && make install && ruby-install --system ruby ${RUBY_VERSION} && rm -rf /ruby-install 

#bundler install
RUN gem install bundler && rm -rf /tmp/* /var/tmp/* /usr/lib/ruby/gems/*/cache/*.gem

WORKDIR /
