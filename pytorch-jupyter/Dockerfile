FROM ubuntu:latest
ENV DEBIAN_FRONTEND noninteractive

RUN apt update && apt upgrade -y
RUN apt install -y vim python3 python3-pip

RUN useradd -rm -d /home/ubuntu -s /bin/bash -g root -G sudo -u 1001 ubuntu -p "$(openssl passwd -1 ubuntu)"
USER ubuntu
WORKDIR /home/ubuntu

ADD requirements.txt /tmp/requirements.txt
RUN python3 -m pip install -U pip
RUN python3 -m pip install -r /tmp/requirements.txt
