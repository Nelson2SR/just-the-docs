---
layout: default
title:  Container
published: true
parent: Docker
comments: true
---

* list all image

```sh
docker image ls
```

* see history

```sh
docker image history jboss/wildfly
```

* Run WildFly container in an interactive mode.

```sh
docker container run -it jboss/wildfly
```

* Restart the container in detached mode:

```sh
docker container run -d jboss/wildfly
```

* list the container

```sh
docker container ls -a
```

* stop container and restart with different options

```sh
docker container stop `docker container ps | grep wildfly | awk '{print $1}'`
```

* restart

```sh
docker container run -d -P --name wildfly jboss/wildfly
```

* stop and remove running container

```sh
docker container stop wildfly
docker container rm wildfly

or
docker container rm -f wildfly
```

* restart

```sh
docker container run -d -p 8080:8080 --name wildfly jboss/wildfly
```
