# PHP VLD Docker

A Docker container to build the PHP [VLD](https://github.com/derickr/vld) extension.

[![License](https://img.shields.io/github/license/cyrilverloop/php-vld-docker)](https://github.com/cyrilverloop/php-vld-docker/blob/trunk/LICENSE)

**This project will only follow [PHP's supported versions](https://www.php.net/supported-versions.php).**

Currently supported OS :
- [Alpine](https://alpinelinux.org/).


## Usage

Add the following lines to your `Dockerfile` depending on your OS.

### Alpine :

```dockerfile
COPY --from=php-vld:latest /root/vld/modules/vld.so /usr/local/lib/php/extensions/no-debug-non-zts-20220829/
COPY --from=php-vld:latest /root/vld.ini /usr/local/etc/php/conf.d/ # To activate the extension.
```


## Build instructions

If you want to build the images :
```shellsession
user@host ~$ cd [PATH_WHERE_TO_PUT_THE_PROJECT] # E.g. ~/projects/
user@host projects$ git clone https://github.com/cyrilverloop/php-vld-docker.git
user@host projects$ cd php-vld-docker
user@host php-vld-docker$ cd alpine/3.17/php8.2 # Change the OS and PHP version according to your needs.
user@host php8.2$ docker build -t php-vld:php8.2-alpine3.17 .
user@host php8.2$ docker tag php-vld:8.2-alpine3.17 php-vld:[SOME_OTHER_TAG]
```
