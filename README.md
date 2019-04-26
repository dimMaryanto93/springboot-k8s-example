# Springboot as service in kubernate (k8s)

Untuk menjalankan springboot di container / pod kubernate kita memerlukan build image docker yang di push ke docker-registry

## Build image menggunakan maven plugin dockerfile

Berikut adalah command untuk melakukan build dan publish image ke [docker.io](https://hub.docker.com)

```bash
mvn clean package dockerfile:build dockerfile:push
```

Setelah di push make sure, image telah ter-created di hub.docker.io. contohnya pada repository berikut [dimmaryanto93/springboot-k8s-example](https://hub.docker.com/r/dimmaryanto93/springboot-k8s-example/tags)

## configure kubernate

System required: 

- [VirtualBox](https://www.virtualbox.org/wiki/Downloads)
- [docker-engine](https://docs.docker.com)
- [minikube](https://kubernetes.io/docs/setup/minikube/)

Setelah semuanya terinstall, kita jalankan service minikube dengan perintah seperti berikut:

```bash
minikube start
```

Berikut outputnya:

```bash
😄  minikube v1.0.0 on darwin (amd64)
🤹  Downloading Kubernetes v1.14.0 images in the background ...
🔥  Creating virtualbox VM (CPUs=2, Memory=2048MB, Disk=20000MB) ...
📶  "minikube" IP address is 192.168.99.109
🐳  Configuring Docker as the container runtime ...
🐳  Version of container runtime is 18.06.2-ce
⌛  Waiting for image downloads to complete ...
✨  Preparing Kubernetes environment ...
🚜  Pulling images required by Kubernetes v1.14.0 ...
🚀  Launching Kubernetes v1.14.0 using kubeadm ... 
⌛  Waiting for pods: apiserver proxy etcd scheduler controller dns
🔑  Configuring cluster permissions ...
🤔  Verifying component health .....
💗  kubectl is now configured to use "minikube"
🏄  Done! Thank you for using minikube!
```
