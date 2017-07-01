# Docker-Node-RED-Logstash
Docker image of [Node-RED](http://nodered.org/) with [logstash plugin](https://github.com/consulthys/node-red-contrib-logstash)

[![Greenkeeper badge](https://badges.greenkeeper.io/ekho/node-red-logstash.svg)](https://greenkeeper.io/)

Run
===

```
docker run -it -p 1880:1880 --name mynodered ekho/node-red-logstash
```

Persisting data
---------------
```
docker run -it -p 1880:1880 -v ./node-red:/data --name mynodered ekho/node-red-logstash
```
Or with named volumes
```
docker volume create --name node_red_user_data
docker run -it -p 1880:1880 -v node_red_user_data:/data --name mynodered ekho/node-red-logstash
```

Docker compose
--------------
```
version: '3'
services:
  nodered:
    image: ekho/node-red-logstash:latest
    ports:
      - "1880:1880"
    volumes:
      - "./node-red:/data"
```
