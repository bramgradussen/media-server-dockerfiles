FROM debian:jessie
MAINTAINER Jeff Sturgis <jeffsturgis@gmail.com>

ENV DEBIAN_FRONTEND noninteractive
RUN echo "deb http://deb.debian.org/debian jessie contrib non-free" >> /etc/apt/sources.list
RUN apt-get update && apt-get install -y -q software-properties-common python git-core
RUN git clone https://github.com/rembo10/headphones.git
RUN cd ./headphones && git checkout $(git tag -l | tail -n1)

ENTRYPOINT ["/usr/bin/python", "headphones/Headphones.py", "--datadir=/mnt/state", "--config=/mnt/state/config.ini", "--nolaunch"]
