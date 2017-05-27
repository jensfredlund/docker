FROM ubuntu:xenial
LABEL maintainer "jens.fredlund@gmail.com"

EXPOSE 53/tcp 53/udp

RUN apt-get update && apt-get install -y bind9

ADD config/named.conf.options /etc/bind/
ADD config/named.conf.local /etc/bind/
ADD config/zones/ /etc/bind/zones/

CMD ["/usr/sbin/named", "-c", "/etc/bind/named.conf", "-g", "-u", "bind"]
