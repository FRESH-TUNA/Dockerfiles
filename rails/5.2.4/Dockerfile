# 루비 베이스 이미지
FROM gomicorp/ruby:2.6.3

ENV RAILS_VERSION 5.2.4

# install node:12, yarn, rails, passenger
RUN curl -sL https://rpm.nodesource.com/setup_12.x | bash - \
    && curl --silent --location https://dl.yarnpkg.com/rpm/yarn.repo | tee /etc/yum.repos.d/yarn.repo \
    && yum install -y nodejs yarn && yum clean all && rm -rf /var/cache/yum \
    && gem install rails -v ${RAILS_VERSION} && rm -rf /tmp/* /var/tmp/* /usr/lib/ruby/gems/*/cache/*.gem
