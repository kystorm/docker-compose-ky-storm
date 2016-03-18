############################################################
# Dockerfile to build uwsgi using python3 container images
# Based on Ubuntu 14.04.4
############################################################

FROM ubuntu:14.04.4
MAINTAINER ky.storm <ky.storm@163.com>

RUN apt-get update
RUN apt-get upgrade -y

# python 3.4 has already installed by os
RUN apt-get install -y \
            python3-pip

# clean apt-get
RUN apt-get autoclean
RUN apt-get clean
RUN apt-get autoremove

# install uwsgi
RUN pip3 install uwsgi
RUN pip3 install -U pip setuptools

# install requirements
COPY ../ky-storm/requirements.txt /var/app/ky-storm/
RUN pip3 install -r /var/app/ky-storm/requirements.txt

# expose ports
EXPOSE 8080

CMD uwsgi --ini /var/app/ky-storm/uwsgi_config.ini