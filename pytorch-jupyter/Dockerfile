FROM ubuntu:latest
ENV DEBIAN_FRONTEND noninteractive

RUN apt update && apt upgrade -y
RUN apt install -y sudo vim python3 python3-pip

RUN useradd -m ubuntu
RUN echo "ubuntu:ubuntu" | chpasswd
RUN adduser ubuntu sudo

USER ubuntu
WORKDIR /home

ADD requirements.txt /tmp/requirements.txt
RUN python3 -m pip install -U pip
RUN python3 -m pip install -r /tmp/requirements.txt
