# hbase-standalone [![Docker Pulls](https://img.shields.io/docker/pulls/pierrezemb/hbase-standalone.svg?style=plastic)](https://hub.docker.com/r/pierrezemb/hbase-standalone/) [![Docker Build](https://img.shields.io/docker/build/pierrezemb/hbase-standalone.svg?style=plastic)](https://hub.docker.com/r/pierrezemb/hbase-standalone/)
Docker images to experiment with HBase 1.3.1 and 2.0

## Why not 1.4.X ?

Standalone mode for 1.4.X is setting port in random...

## Usage
```
docker run -it \
        -p 8080:8080 \
        -p 9090:9090 \
        -p 2181:2181 \
        -p 16000:16000 \
        -p 16010:16010 \
        -p 16020:16020 \
        -p 16030:16030 \
      pierrezemb/hbase-standalone:2.0.0-beta-1
```

#### HBase Master server interface
http://localhost:16010/master-status

#### Verifying HBase REST interface
```
# HBase Version
[user@host ~]$ curl http://localhost:8080/version/cluster

# Cluster Status
[user@host ~]$ curl http://localhost:8080/status/cluster

# Table List
[user@host ~]$ curl http://localhost:8080/
```
### Accessing the HBase shell
```
[user@host ~]$ docker exec -it hbase bash
user@host:/opt# hbase shell
```

## Build it

```
docker build -t pierrezemb/hbase-standalone:2.0.0-beta-1 .
```