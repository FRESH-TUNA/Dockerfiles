FROM debian:buster-20200607
RUN apt update \
    && apt install -y curl gnupg2 ca-certificates lsb-release \            
    && rm -rf /var/lib/apt/lists/*

RUN echo "deb http://nginx.org/packages/debian `lsb_release -cs` nginx" \
    | tee /etc/apt/sources.list.d/nginx.list \
    && curl -kfsSL https://nginx.org/keys/nginx_signing.key | apt-key add - \
    && apt-key fingerprint ABF5BD827BD9BF62 | grep '573B FD6B 3D8F BC64 1079  A6AB ABF5 BD82 7BD9 BF62'

RUN apt update \
    && apt install -y nginx=1.14.2-2+deb10u1 \            
    && rm -rf /var/lib/apt/lists/*

COPY ./nginx.supervisord.conf /etc/supervisor/conf.d

ENTRYPOINT ["supervisord"]
