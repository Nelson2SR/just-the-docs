---
layout: default
title:  Volumes
published: true
parent: Docker
---

What is data volumes?
 > In container, data can map directly in localhost

* create a data volumes

```sh
docker run -d -P --name web -v /webapp training/webapp python app.py
```

* load a local directory as a data volumes

```sh
docker run -d -P --name web -v /src/webapp:/opt/webapp training/webapp python app.py
```

* modify the permission, default rw

```sh
docker run -d -P --name web -v /src/webapp:/opt/webapp:ro training/webapp python app.py
```

* load a local file as a data volumes

```sh
docker run --rm -it -v ~/.bash_history:/.bash_history ubuntu /bin/bash
```

* data volumes container, used for data sharing between multiple container

```sh
docker run -it -v /dbdata --name dbdata ubuntu
```

* in other container, load the volumes

```sh
docker run -it --volumes-from dbdata --name db1 ubuntu
docker run -it --volumes-from dbdata --name db2 ubuntu
```

* back up data volumes

```sh
docker run --volumes-from dbdata -v $(pwd):/backup --name worker ubuntu tar cvf /backup/backup.tar /dbdata
```

* resume the data volumes

```sh
docker run -v /dbdata --name dbdata2 ubuntu /bin/bash
docker run --volumes-from dbdata2 -v $(pwd):/backup bushbox tar xvf /backup/backup.tar
```
