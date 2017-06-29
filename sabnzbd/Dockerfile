FROM ubuntu:latest
MAINTAINER Jeff Sturgis <jeffsturgis@gmail.com>
ENV DEBIAN_FRONTEND noninteractive

RUN apt-get clean && apt-get update
RUN apt-get -y install software-properties-common locales && locale-gen en_US en_US.UTF-8
RUN add-apt-repository -y ppa:jcfp/ppa
RUN add-apt-repository -y ppa:jcfp/sab-addons
RUN apt-get -q update
RUN apt-mark hold initscripts udev plymouth mountall

RUN apt-get install -qy --force-yes sabnzbdplus par2-tbb python-sabyenc unrar unzip
ENV LANG=en_US.UTF-8

ENTRYPOINT ["/usr/bin/sabnzbdplus", "-b", "0", "-f", "/mnt/state/sabnzbd.ini", "--server", ":8080"]
