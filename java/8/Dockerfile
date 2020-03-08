FROM centos:8

ENV OPEN_JDK_VERSION 1.8.0
ENV LESSCHARSET utf-8

# update packages and install required packages
RUN yum install -y which tar \
    wget git sudo mysql-devel make libcurl-devel crontabs logrotate && yum clean all \
    && yum clean all && rm -rf /var/cache/yum && git config --global i18n.commitEncoding utf-8 \
    && git config --global i18n.logOutputEncoding utf-8

RUN yum install -y java-${OPEN_JDK_VERSION}-openjdk