# Alpine container with Easy RSA PKI & OpenVPN server


```
docker build -t "openvpn:latest" .
```

```
docker run --device /dev/net/tun --privileged -p 1194:1194/udp --name openvpn openvpn:latest
```
