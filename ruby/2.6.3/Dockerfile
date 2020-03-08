FROM amazonlinux

ENV RUBY_VERSION 2.6.3
ENV RUBY_INSTALL_PACKAGE 0.7.0
ENV LESSCHARSET utf-8

# update packages and install required packages
RUN yum install -y which tar gzip procps \
    patch libyaml-devel libffi-devel glibc-headers autoconf \
    gcc-c++ glibc-devel readline-devel zlib-devel openssl-devel \
    bzip2 automake libtool bison shadow-utils.x86_64 \
    wget git sudo mysql-devel make libcurl-devel crontabs logrotate && yum clean all \
    && yum clean all && rm -rf /var/cache/yum && git config --global i18n.commitEncoding utf-8 \
    && git config --global i18n.logOutputEncoding utf-8

#ruby install
WORKDIR /ruby-install
RUN wget -O ruby-install-${RUBY_INSTALL_PACKAGE}.tar.gz https://github.com/postmodern/ruby-install/archive/v${RUBY_INSTALL_PACKAGE}.tar.gz \
    && tar -xzvf ruby-install-${RUBY_INSTALL_PACKAGE}.tar.gz \
    && cd /ruby-install/ruby-install-${RUBY_INSTALL_PACKAGE}/ \
    && make install && ruby-install --system ruby ${RUBY_VERSION} && rm -rf /ruby-install \
    && cd / \
    && rm -rf /ruby-install \
    && gem install bundler && rm -rf /tmp/* /var/tmp/* /usr/lib/ruby/gems/*/cache/*.gem
WORKDIR /
