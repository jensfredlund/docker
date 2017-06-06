FROM ubuntu:xenial
LABEL maintainer "jens.fredlund@gmail.com"
LABEL description="Ubuntu xenial Docker container with Bind9 and one example zone"
LABEL version="1.0"

EXPOSE 53/tcp 53/udp

RUN apt-get update && apt-get install -y bind9 \
&& mkdir -vp /var/run/named \
&& mkdir -vp /var/cache/named \
&& mkdir -vp /var/log/named \
&& chown -vR bind:bind /var/run/named \
&& chown -vR bind:bind /var/cache/named \
&& chown -vR bind:bind /var/log/named

ADD config/named.conf.options /etc/bind/
ADD config/named.conf.local /etc/bind/
ADD config/zones/ /etc/bind/zones/

CMD ["/usr/sbin/named", "-c", "/etc/bind/named.conf", "-g", "-u", "bind"]
