---
layout: post
title:  "[Mac] Docker & NodeJS"
date:   2021-12-07 23:00:00 +0900
categories: [mac]
---

#### iTerm2 다운로드
```bash
softwareupdate –install-rosetta
```
<br>

#### 도커 다운로드
[Docker Desktop – Mac with Apple chip](https://docs.docker.com/desktop/mac/apple-silicon)

<br>

#### 도커 셋업
```bash
docker pull node:14.17.6
docker images
```
```bash
REPOSITORY   TAG       IMAGE ID       CREATED       SIZE  
node         14.17.6   8beedd044dbc   2 weeks ago   891MB
```
<br>

```bash
docker run -d -it –name node_14_17_6 -v /Users/joyplug/Documents/Project/docker/node_14_17_6:/app node:14.17.6
docker ps -a
```
```bash
CONTAINER ID   IMAGE          COMMAND                  CREATED              STATUS          PORTS     NAMES
b5c97eb3507b   node:14.17.6   "docker-entrypoint.s…"   About a minute ago   Up 58 seconds             node_14_17_6
```
<br>

```bash
docker exec -it node_14_17_6 /bin/bash
docker commit node_14_17_6 node_14_17_6:0.0.1
docker images
```
```bash
REPOSITORY     TAG       IMAGE ID       CREATED          SIZE
node_14_17_6   0.0.1     3a9f19bebb20   20 seconds ago   891MB
node           14.17.6   8beedd044dbc   2 weeks ago      891MB
```
<br>

```bash
docker stop node_14_17_6
docker ps -a
```
```bash
CONTAINER ID   IMAGE          COMMAND                  CREATED          STATUS                       PORTS     NAMES
b5c97eb3507b   node:14.17.6   "docker-entrypoint.s…"   11 minutes ago   Exited (137) 4 seconds ago             node_14_17_6
```
