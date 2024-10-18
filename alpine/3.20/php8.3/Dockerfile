FROM php:8.3-alpine3.20
RUN apk update \
    && apk add --no-cache autoconf g++ make git \
    && apk del --purge \
    && cd \
    && git clone https://github.com/derickr/vld.git \
    && cd ~/vld/ \
    && phpize \
    && ./configure \
    && make \
    && echo -e "extension=vld.so\nvld.active=1" > ~/vld.ini
