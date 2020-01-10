FROM ubuntu:latest
MAINTAINER Keith Sterling (keith@chatillyc.om

ENV container docker

VOLUME ["/sys/fs/cgroup"]
VOLUME ["/run"]

RUN \
  echo Installing dev tools && \
  apt-get update && \
  apt-get -y upgrade && \
  apt-get install -y software-properties-common && \
  apt-get install -y build-essential && \
  apt-get install -y git

RUN \
  echo Installing Python 3.6 && \
  add-apt-repository ppa:jonathonf/python-3.6 && \
  apt-get update && \
  apt-get install -y python3.6 && \
  rm /usr/bin/python3 && \
  ln -s /usr/bin/python3.6 /usr/bin/python3

RUN \
  echo installing Pip 3 && \
  apt-get install -y python3-pip && \
  pip3 install --upgrade pip

RUN mkdir /opt/program-y

WORKDIR /opt/program-y

RUN \
  echo Installing Program-y && \
  pip3 install programy

EXPOSE 8080
EXPOSE 22


