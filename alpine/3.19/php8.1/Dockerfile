FROM php:8.1-alpine3.19
RUN apk update \
    && apk add --no-cache autoconf g++ make git \
    && apk del --purge \
    && cd \
    && git clone https://github.com/derickr/vld.git \
    && cd ~/vld/ \
    && git checkout df1c52c4cb62e5ff31e1b72e3f11df9a45ee567a \
    && phpize \
    && ./configure \
    && make \
    && echo -e "extension=vld.so\nvld.active=1" > ~/vld.ini
