# 루비 베이스 이미지
FROM gomicorp/ruby:2.6.3

ENV RAILS_VERSION 6.0.2.1

# install node:12, yarn, rails
RUN curl -sL https://rpm.nodesource.com/setup_12.x | bash - \
    && yum install -y nodejs yarn && yum clean all \
    && gem install rails -v ${RAILS_VERSION} && rm -rf /tmp/* /var/tmp/* /usr/lib/ruby/gems/*/cache/*.gem
