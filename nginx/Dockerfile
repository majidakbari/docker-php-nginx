FROM nginx:1.13.11

MAINTAINER "Majid Akbari <majidakbariiii@gmail.com>"

ARG WWW_DATA_USER_ID

COPY ./config/default.conf /etc/nginx/conf.d/

RUN usermod -u ${WWW_DATA_USER_ID} www-data \
    && groupmod -g ${WWW_DATA_USER_ID} www-data
