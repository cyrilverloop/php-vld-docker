FROM php:8.2-alpine3.17
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
