FROM ubuntu:latest
MAINTAINER Jeff Sturgis <jeffsturgis@gmail.com>
ENV DEBIAN_FRONTEND noninteractive

RUN apt-get -q update
RUN apt-get -y install locales && locale-gen en_US en_US.UTF-8
RUN apt-get -y install software-properties-common
RUN add-apt-repository -y ppa:deluge-team/ppa
RUN apt-get -q update
RUN apt-get -yq upgrade
RUN apt-mark hold initscripts udev plymouth mountall

RUN apt-get install -qy --force-yes deluged deluge-web
ADD start.sh /start.sh

CMD ["/start.sh"]
