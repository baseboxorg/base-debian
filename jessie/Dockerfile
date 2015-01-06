FROM debian:jessie

<<<<<<< HEAD
ENV DEBIAN_FRONTEND noninteractive

RUN apt-get update && apt-get -y install git curl wget locales
=======
RUN apt-get update && DEBIAN_FRONTEND=noninteractive apt-get -y install git curl wget locales nano
>>>>>>> FETCH_HEAD

RUN dpkg-reconfigure locales && \
  locale-gen C.UTF-8 && \
  /usr/sbin/update-locale LANG=C.UTF-8
<<<<<<< HEAD

=======
  
>>>>>>> FETCH_HEAD
RUN echo 'en_US.UTF-8 UTF-8' >> /etc/locale.gen && \
  locale-gen

ENV LC_ALL C.UTF-8
ENV LANG en_US.UTF-8
ENV LANGUAGE en_US.UTF-8
<<<<<<< HEAD



=======
>>>>>>> FETCH_HEAD
