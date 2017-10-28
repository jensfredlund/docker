# Ubuntu container with a crontab

```
jf@Tzunami:~/docker/cron$ make
docker build -t cron:latest .
Sending build context to Docker daemon 5.632 kB
Step 1 : FROM ubuntu:xenial
xenial: Pulling from library/ubuntu
ae79f2514705: Pull complete 
5ad56d5fc149: Pull complete 
170e558760e8: Pull complete 
395460e233f5: Pull complete 
6f01dc62e444: Pull complete
```

```
jf@Tzunami:~/docker/cron$ docker images
REPOSITORY          TAG                 IMAGE ID            CREATED              SIZE
cron                latest              300f8207a6a1        About a minute ago   141 MB
ubuntu              xenial              747cb2d60bbe        2 weeks ago          122 MB
```

```
jf@Tzunami:~/docker/cron$ docker run -d cron:latest
4ab1ad96eca63e76e1bed8db9eff8873991e44ba654acd6783d3d7e3b45cea42
```

```
jf@Tzunami:~/docker/cron$ docker ps
CONTAINER ID        IMAGE               COMMAND               CREATED             STATUS              PORTS               NAMES
4ab1ad96eca6        cron:latest         "/usr/sbin/cron -f"   16 seconds ago      Up 15 seconds                           hungry_wing
```

```
jf@Tzunami:~/docker/cron$ docker exec 4ab1ad96eca6 tail -F /var/log/cron.log
Cron output
Cron output
Cron output
```
