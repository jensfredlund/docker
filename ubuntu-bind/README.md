# Ubuntu xenial container with bind9 and one example zone

```
$ docker build -t "bind:latest" .
$ docker run -d -p 53:53/udp -p 53:53 --name bind bind:latest
```
