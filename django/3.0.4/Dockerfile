FROM python:3.8.1-slim

ENV DJANGO_VERSION=3.0.4

RUN apt update \
    && apt install -y gcc \            
    && rm -rf /var/lib/apt/lists/* \
    && pip3 --no-cache-dir install django==${DJANGO_VERSION}
