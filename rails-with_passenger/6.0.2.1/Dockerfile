# install passenger
FROM gomicorp/rails:6.0.2.1

RUN gem install passenger && rm -rf /tmp/* /var/tmp/* /usr/lib/ruby/gems/*/cache/*.gem \
    && passenger-install-nginx-module --auto --auto-download --prefix=/opt/nginx --languages ruby
