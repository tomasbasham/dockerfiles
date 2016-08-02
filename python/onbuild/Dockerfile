FROM python:4.5.1-alpine

LABEL com.tomasbasham.maintainer "Tomas Basham <me@tomasbasham.co.uk>" \
      com.tomasbasham.description "Python"

RUN mkdir -p /usr/src/app
WORKDIR /usr/src/app

ONBUILD COPY requirements.txt /usr/src/app
ONBUILD RUN pip install --no-cache-dir -r requirements.txt
