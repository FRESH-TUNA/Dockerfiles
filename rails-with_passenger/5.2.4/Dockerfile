# install passenger
FROM gomicorp/rails:5.2.4

# logrotate and passenger install
RUN yum install -y logrotate && yum clean all \
    && gem install passenger && rm -rf /tmp/* /var/tmp/* /usr/lib/ruby/gems/*/cache/*.gem \
    && passenger-install-nginx-module --auto --auto-download --prefix=/opt/nginx --languages ruby
