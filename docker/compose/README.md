Example of running `docker-compose`. 
Make sure the `docker-compose.yml` file is present in the directory and run `docker-compose`.

```
bash-3.2$ ls
docker-compose.yml

bash-3.2$ docker-compose up
Pulling pg (postgres:latest)...
latest: Pulling from library/postgres
386a066cd84a: Already exists
e6dd80b38d38: Pull complete
9cd706823821: Pull complete
40c17ac202a9: Pull complete
7380b383ba3d: Pull complete
538e418b46ce: Pull complete
c3b9d41b7758: Pull complete
dd4f9522dd30: Pull complete
920e548f9635: Pull complete
628af7ef2ee5: Pull complete
```

In another terminal window:

```
mymac:kubernetes tdongsi$ docker ps
CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS              PORTS               NAMES
c4aea386ee3e        nginx               "nginx -g 'daemon off"   5 days ago          Up 2 minutes        80/tcp, 443/tcp     compose_frontend_1
f4eee1729389        postgres            "/docker-entrypoint.s"   5 days ago          Up 2 minutes        5432/tcp            compose_pg_1
mymac:kubernetes tdongsi$ docker exec -it compose_frontend_1 bash
root@c4aea386ee3e:/#

root@c4aea386ee3e:/# ping pg
PING pg (172.17.0.2): 56 data bytes
64 bytes from 172.17.0.2: icmp_seq=0 ttl=64 time=1.096 ms
64 bytes from 172.17.0.2: icmp_seq=1 ttl=64 time=0.118 ms
64 bytes from 172.17.0.2: icmp_seq=2 ttl=64 time=0.152 ms
64 bytes from 172.17.0.2: icmp_seq=3 ttl=64 time=0.112 ms
```

As you can see, inside the container `compose_frontend_1`, you can `ping` the other container `pg`.
