FROM alpine:latest
LABEL maintainer "jens.fredlund@gmail.com"
LABEL description="OpenVPN POC"
LABEL version="1.0"

EXPOSE 1194/udp

###
# Environment variables
###
ENV PKI_CN=server
ENV DHPARAM_BITS=1024
ENV OPENVPN_KEYS_DIR=/etc/openvpn/keys

# Install packages
RUN apk add --update \
    openvpn \
    openssl \
    easy-rsa

###
# Create PKI for the OpenVPN server
###
RUN cp -Rv /usr/share/easy-rsa /root/easy-rsa

ADD files/easy_rsa.vars /root/easy-rsa/vars

RUN cd /root/easy-rsa && \
    ./easyrsa init-pki && \
    echo "$PKI_CN" | ./easyrsa build-ca nopass && \
    echo "$PKI_CN" | ./easyrsa gen-req server nopass && \
    echo "yes" | ./easyrsa sign-req server server

###
# OpenVPN clients
###
RUN cd /root/easy-rsa && \
    echo "client1" | ./easyrsa gen-req client1 nopass && \
    echo "yes" | ./easyrsa sign-req client client1


###
# Create & copy OpenVPN server keys & server config
###
RUN mkdir -vp $OPENVPN_KEYS_DIR && \
    /usr/sbin/openvpn --genkey --secret $OPENVPN_KEYS_DIR/ta.key && \
    /usr/bin/openssl dhparam -out $OPENVPN_KEYS_DIR/dh1024.pem 1024 && \
    cp -v /root/easy-rsa/pki/ca.crt $OPENVPN_KEYS_DIR && \
    cp -v /root/easy-rsa/pki/issued/server.crt $OPENVPN_KEYS_DIR && \
    cp -v /root/easy-rsa/pki/private/server.key $OPENVPN_KEYS_DIR

ADD files/server.conf /etc/openvpn

###
# Misc things to run OpenVPN
###

CMD ["/usr/sbin/openvpn", "--config", "/etc/openvpn/server.conf"]
