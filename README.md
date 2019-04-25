# Springboot as service in kubernate (k8s)

Untuk menjalankan springboot di container / pod kubernate kita memerlukan build image docker yang di push ke docker-registry

## Build image menggunakan maven plugin dockerfile

Berikut adalah command untuk melakukan build dan publish image ke [docker.io](https://hub.docker.com)

```bash
mvn clean package dockerfile:build dockerfile:push
```
