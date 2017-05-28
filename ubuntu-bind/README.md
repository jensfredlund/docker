# Ubuntu xenial container with bind9 and one example zone

```
jf@docker01:/home/jf$ git clone https://github.com/jensfredlund/docker.git
Cloning into 'docker'...
remote: Counting objects: 17, done.
remote: Compressing objects: 100% (13/13), done.
remote: Total 17 (delta 2), reused 16 (delta 1), pack-reused 0
Unpacking objects: 100% (17/17), done.
Checking connectivity... done.

jf@docker01:/home/jf$ cd docker/ubuntu-bind ; ls
Dockerfile  README.md  config

jf@docker01$:/home/jf/docker/ubuntu-bind$ docker build -t "bind:latest" .
Allot of build output...

jf@docker01:/home/jf/docker/ubuntu-bind$ docker run -p 53:53/udp -p 53:53 --name bind bind:latest
28-May-2017 19:35:57.887 starting BIND 9.10.3-P4-Ubuntu <id:ebd72b3> -c /etc/bind/named.conf -g -u bind
28-May-2017 19:35:57.887 built with '--prefix=/usr' '--mandir=/usr/share/man' '--libdir=/usr/lib/x86_64-linux-gnu' '--infodir=/usr/share/info' '--sysconfdir=/etc/bind' '--localstatedir=/' '--enable-threads' '--enable-largefile' '--with-libtool' '--enable-shared' '--enable-static' '--with-openssl=/usr' '--with-gssapi=/usr' '--with-gnu-ld' '--with-geoip=/usr' '--with-atf=no' '--enable-ipv6' '--enable-rrl' '--enable-filter-aaaa' '--enable-native-pkcs11' '--with-pkcs11=/usr/lib/x86_64-linux-gnu/softhsm/libsofthsm2.so' 'CFLAGS=-g -O2 -fPIE -fstack-protector-strong -Wformat -Werror=format-security -fno-strict-aliasing -fno-delete-null-pointer-checks -DNO_VERSION_DATE' 'LDFLAGS=-Wl,-Bsymbolic-functions -fPIE -pie -Wl,-z,relro -Wl,-z,now' 'CPPFLAGS=-Wdate-time -D_FORTIFY_SOURCE=2 -DDIG_SIGCHASE'
28-May-2017 19:35:57.887 ----------------------------------------------------
28-May-2017 19:35:57.887 BIND 9 is maintained by Internet Systems Consortium,
28-May-2017 19:35:57.887 Inc. (ISC), a non-profit 501(c)(3) public-benefit 
28-May-2017 19:35:57.887 corporation.  Support and training for BIND 9 are 
28-May-2017 19:35:57.887 available at https://www.isc.org/support
28-May-2017 19:35:57.887 ----------------------------------------------------
28-May-2017 19:35:57.887 found 3 CPUs, using 3 worker threads
28-May-2017 19:35:57.887 using 2 UDP listeners per interface
28-May-2017 19:35:57.888 using up to 4096 sockets
28-May-2017 19:35:57.898 loading configuration from '/etc/bind/named.conf'
28-May-2017 19:35:57.900 reading built-in trusted keys from file '/etc/bind/bind.keys'
28-May-2017 19:35:57.900 initializing GeoIP Country (IPv4) (type 1) DB
28-May-2017 19:35:57.901 GEO-106FREE 20160408 Bu
28-May-2017 19:35:57.901 initializing GeoIP Country (IPv6) (type 12) DB
28-May-2017 19:35:57.901 GEO-106FREE 20160408 Bu
28-May-2017 19:35:57.901 GeoIP City (IPv4) (type 2) DB not available
28-May-2017 19:35:57.901 GeoIP City (IPv4) (type 6) DB not available
28-May-2017 19:35:57.901 GeoIP City (IPv6) (type 30) DB not available
28-May-2017 19:35:57.901 GeoIP City (IPv6) (type 31) DB not available
28-May-2017 19:35:57.901 GeoIP Region (type 3) DB not available
28-May-2017 19:35:57.901 GeoIP Region (type 7) DB not available
28-May-2017 19:35:57.901 GeoIP ISP (type 4) DB not available
28-May-2017 19:35:57.901 GeoIP Org (type 5) DB not available
28-May-2017 19:35:57.901 GeoIP AS (type 9) DB not available
28-May-2017 19:35:57.901 GeoIP Domain (type 11) DB not available
28-May-2017 19:35:57.901 GeoIP NetSpeed (type 10) DB not available
28-May-2017 19:35:57.902 using default UDP/IPv4 port range: [32768, 60999]
28-May-2017 19:35:57.902 using default UDP/IPv6 port range: [32768, 60999]
28-May-2017 19:35:57.905 listening on IPv6 interfaces, port 53
28-May-2017 19:35:57.926 listening on IPv4 interface lo, 127.0.0.1#53
28-May-2017 19:35:57.928 listening on IPv4 interface eth0, 172.17.0.2#53
28-May-2017 19:35:57.930 generating session key for dynamic DNS
28-May-2017 19:35:57.931 sizing zone task pool based on 6 zones
28-May-2017 19:35:57.937 set up managed keys zone for view _default, file 'managed-keys.bind'
28-May-2017 19:35:57.937 automatic empty zone: 10.IN-ADDR.ARPA
28-May-2017 19:35:57.937 automatic empty zone: 16.172.IN-ADDR.ARPA
28-May-2017 19:35:57.937 automatic empty zone: 17.172.IN-ADDR.ARPA
28-May-2017 19:35:57.937 automatic empty zone: 18.172.IN-ADDR.ARPA
28-May-2017 19:35:57.937 automatic empty zone: 19.172.IN-ADDR.ARPA
28-May-2017 19:35:57.937 automatic empty zone: 20.172.IN-ADDR.ARPA
28-May-2017 19:35:57.937 automatic empty zone: 21.172.IN-ADDR.ARPA
28-May-2017 19:35:57.937 automatic empty zone: 22.172.IN-ADDR.ARPA
28-May-2017 19:35:57.937 automatic empty zone: 23.172.IN-ADDR.ARPA
28-May-2017 19:35:57.937 automatic empty zone: 24.172.IN-ADDR.ARPA
28-May-2017 19:35:57.937 automatic empty zone: 25.172.IN-ADDR.ARPA
28-May-2017 19:35:57.937 automatic empty zone: 26.172.IN-ADDR.ARPA
28-May-2017 19:35:57.937 automatic empty zone: 27.172.IN-ADDR.ARPA
28-May-2017 19:35:57.937 automatic empty zone: 28.172.IN-ADDR.ARPA
28-May-2017 19:35:57.937 automatic empty zone: 29.172.IN-ADDR.ARPA
28-May-2017 19:35:57.938 automatic empty zone: 30.172.IN-ADDR.ARPA
28-May-2017 19:35:57.938 automatic empty zone: 31.172.IN-ADDR.ARPA
28-May-2017 19:35:57.938 automatic empty zone: 168.192.IN-ADDR.ARPA
28-May-2017 19:35:57.938 automatic empty zone: 64.100.IN-ADDR.ARPA
28-May-2017 19:35:57.938 automatic empty zone: 65.100.IN-ADDR.ARPA
28-May-2017 19:35:57.938 automatic empty zone: 66.100.IN-ADDR.ARPA
28-May-2017 19:35:57.938 automatic empty zone: 67.100.IN-ADDR.ARPA
28-May-2017 19:35:57.938 automatic empty zone: 68.100.IN-ADDR.ARPA
28-May-2017 19:35:57.938 automatic empty zone: 69.100.IN-ADDR.ARPA
28-May-2017 19:35:57.938 automatic empty zone: 70.100.IN-ADDR.ARPA
28-May-2017 19:35:57.938 automatic empty zone: 71.100.IN-ADDR.ARPA
28-May-2017 19:35:57.938 automatic empty zone: 72.100.IN-ADDR.ARPA
28-May-2017 19:35:57.938 automatic empty zone: 73.100.IN-ADDR.ARPA
28-May-2017 19:35:57.939 automatic empty zone: 74.100.IN-ADDR.ARPA
28-May-2017 19:35:57.939 automatic empty zone: 75.100.IN-ADDR.ARPA
28-May-2017 19:35:57.939 automatic empty zone: 76.100.IN-ADDR.ARPA
28-May-2017 19:35:57.939 automatic empty zone: 77.100.IN-ADDR.ARPA
28-May-2017 19:35:57.939 automatic empty zone: 78.100.IN-ADDR.ARPA
28-May-2017 19:35:57.939 automatic empty zone: 79.100.IN-ADDR.ARPA
28-May-2017 19:35:57.939 automatic empty zone: 80.100.IN-ADDR.ARPA
28-May-2017 19:35:57.939 automatic empty zone: 81.100.IN-ADDR.ARPA
28-May-2017 19:35:57.939 automatic empty zone: 82.100.IN-ADDR.ARPA
28-May-2017 19:35:57.939 automatic empty zone: 83.100.IN-ADDR.ARPA
28-May-2017 19:35:57.939 automatic empty zone: 84.100.IN-ADDR.ARPA
28-May-2017 19:35:57.939 automatic empty zone: 85.100.IN-ADDR.ARPA
28-May-2017 19:35:57.939 automatic empty zone: 86.100.IN-ADDR.ARPA
28-May-2017 19:35:57.939 automatic empty zone: 87.100.IN-ADDR.ARPA
28-May-2017 19:35:57.939 automatic empty zone: 88.100.IN-ADDR.ARPA
28-May-2017 19:35:57.939 automatic empty zone: 89.100.IN-ADDR.ARPA
28-May-2017 19:35:57.939 automatic empty zone: 90.100.IN-ADDR.ARPA
28-May-2017 19:35:57.939 automatic empty zone: 91.100.IN-ADDR.ARPA
28-May-2017 19:35:57.939 automatic empty zone: 92.100.IN-ADDR.ARPA
28-May-2017 19:35:57.940 automatic empty zone: 93.100.IN-ADDR.ARPA
28-May-2017 19:35:57.940 automatic empty zone: 94.100.IN-ADDR.ARPA
28-May-2017 19:35:57.940 automatic empty zone: 95.100.IN-ADDR.ARPA
28-May-2017 19:35:57.940 automatic empty zone: 96.100.IN-ADDR.ARPA
28-May-2017 19:35:57.940 automatic empty zone: 97.100.IN-ADDR.ARPA
28-May-2017 19:35:57.940 automatic empty zone: 98.100.IN-ADDR.ARPA
28-May-2017 19:35:57.940 automatic empty zone: 99.100.IN-ADDR.ARPA
28-May-2017 19:35:57.940 automatic empty zone: 100.100.IN-ADDR.ARPA
28-May-2017 19:35:57.940 automatic empty zone: 101.100.IN-ADDR.ARPA
28-May-2017 19:35:57.940 automatic empty zone: 102.100.IN-ADDR.ARPA
28-May-2017 19:35:57.940 automatic empty zone: 103.100.IN-ADDR.ARPA
28-May-2017 19:35:57.940 automatic empty zone: 104.100.IN-ADDR.ARPA
28-May-2017 19:35:57.940 automatic empty zone: 105.100.IN-ADDR.ARPA
28-May-2017 19:35:57.940 automatic empty zone: 106.100.IN-ADDR.ARPA
28-May-2017 19:35:57.940 automatic empty zone: 107.100.IN-ADDR.ARPA
28-May-2017 19:35:57.940 automatic empty zone: 108.100.IN-ADDR.ARPA
28-May-2017 19:35:57.940 automatic empty zone: 109.100.IN-ADDR.ARPA
28-May-2017 19:35:57.940 automatic empty zone: 110.100.IN-ADDR.ARPA
28-May-2017 19:35:57.940 automatic empty zone: 111.100.IN-ADDR.ARPA
28-May-2017 19:35:57.941 automatic empty zone: 112.100.IN-ADDR.ARPA
28-May-2017 19:35:57.941 automatic empty zone: 113.100.IN-ADDR.ARPA
28-May-2017 19:35:57.941 automatic empty zone: 114.100.IN-ADDR.ARPA
28-May-2017 19:35:57.941 automatic empty zone: 115.100.IN-ADDR.ARPA
28-May-2017 19:35:57.941 automatic empty zone: 116.100.IN-ADDR.ARPA
28-May-2017 19:35:57.941 automatic empty zone: 117.100.IN-ADDR.ARPA
28-May-2017 19:35:57.941 automatic empty zone: 118.100.IN-ADDR.ARPA
28-May-2017 19:35:57.941 automatic empty zone: 119.100.IN-ADDR.ARPA
28-May-2017 19:35:57.941 automatic empty zone: 120.100.IN-ADDR.ARPA
28-May-2017 19:35:57.941 automatic empty zone: 121.100.IN-ADDR.ARPA
28-May-2017 19:35:57.941 automatic empty zone: 122.100.IN-ADDR.ARPA
28-May-2017 19:35:57.941 automatic empty zone: 123.100.IN-ADDR.ARPA
28-May-2017 19:35:57.941 automatic empty zone: 124.100.IN-ADDR.ARPA
28-May-2017 19:35:57.941 automatic empty zone: 125.100.IN-ADDR.ARPA
28-May-2017 19:35:57.941 automatic empty zone: 126.100.IN-ADDR.ARPA
28-May-2017 19:35:57.941 automatic empty zone: 127.100.IN-ADDR.ARPA
28-May-2017 19:35:57.941 automatic empty zone: 254.169.IN-ADDR.ARPA
28-May-2017 19:35:57.942 automatic empty zone: 2.0.192.IN-ADDR.ARPA
28-May-2017 19:35:57.942 automatic empty zone: 100.51.198.IN-ADDR.ARPA
28-May-2017 19:35:57.942 automatic empty zone: 113.0.203.IN-ADDR.ARPA
28-May-2017 19:35:57.942 automatic empty zone: 255.255.255.255.IN-ADDR.ARPA
28-May-2017 19:35:57.942 automatic empty zone: 0.0.0.0.0.0.0.0.0.0.0.0.0.0.0.0.0.0.0.0.0.0.0.0.0.0.0.0.0.0.0.0.IP6.ARPA
28-May-2017 19:35:57.942 automatic empty zone: 1.0.0.0.0.0.0.0.0.0.0.0.0.0.0.0.0.0.0.0.0.0.0.0.0.0.0.0.0.0.0.0.IP6.ARPA
28-May-2017 19:35:57.942 automatic empty zone: D.F.IP6.ARPA
28-May-2017 19:35:57.942 automatic empty zone: 8.E.F.IP6.ARPA
28-May-2017 19:35:57.942 automatic empty zone: 9.E.F.IP6.ARPA
28-May-2017 19:35:57.942 automatic empty zone: A.E.F.IP6.ARPA
28-May-2017 19:35:57.942 automatic empty zone: B.E.F.IP6.ARPA
28-May-2017 19:35:57.942 automatic empty zone: 8.B.D.0.1.0.0.2.IP6.ARPA
28-May-2017 19:35:57.942 automatic empty zone: EMPTY.AS112.ARPA
28-May-2017 19:35:57.947 configuring command channel from '/etc/bind/rndc.key'
28-May-2017 19:35:57.947 command channel listening on 127.0.0.1#953
28-May-2017 19:35:57.947 configuring command channel from '/etc/bind/rndc.key'
28-May-2017 19:35:57.947 command channel listening on ::1#953
28-May-2017 19:35:57.947 not using config file logging statement for logging due to -g option
28-May-2017 19:35:57.948 managed-keys-zone: loaded serial 0
28-May-2017 19:35:57.950 zone 0.in-addr.arpa/IN: loaded serial 1
28-May-2017 19:35:57.957 zone 127.in-addr.arpa/IN: loaded serial 1
28-May-2017 19:35:57.964 zone 255.in-addr.arpa/IN: loaded serial 1
28-May-2017 19:35:57.966 zone example.com/IN: example.com/MX 'mail.example.com' has no address records (A or AAAA)
28-May-2017 19:35:57.967 zone example.com/IN: example.com/MX 'mail2.example.com' has no address records (A or AAAA)
28-May-2017 19:35:57.967 zone example.com/IN: loaded serial 2017052801
28-May-2017 19:35:57.969 zone localhost/IN: loaded serial 2
28-May-2017 19:35:57.969 all zones loaded
28-May-2017 19:35:57.971 running
28-May-2017 19:35:57.971 zone example.com/IN: sending notifies (serial 2017052801)
28-May-2017 19:35:57.973 client 172.17.0.1#57812: received notify for zone 'example.com'
```
