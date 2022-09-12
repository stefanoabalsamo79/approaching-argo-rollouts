### Minikube and requirements

---
***Prerequisites:***
1. [`docker`](https://www.docker.com/)
2. [`kubectl`](https://kubernetes.io/docs/tasks/tools/)
3. [`helm`](https://helm.sh/)
4. [`minikube`](https://minikube.sigs.k8s.io/docs/)

---

#### Makefile targets overview

```bash
minikube start
```

```bash
minikube stop
```
```bash
minikube delete
```

#### Create our own minikube cluster:
```bash
❯ make minikube_start
minikube start
😄  minikube v1.26.0 on Darwin 11.3.1
✨  Automatically selected the docker driver
📌  Using Docker Desktop driver with root privileges
👍  Starting control plane node minikube in cluster minikube
🚜  Pulling base image ...
🔥  Creating docker container (CPUs=2, Memory=4000MB) ...
🐳  Preparing Kubernetes v1.24.1 on Docker 20.10.17 ...
    ▪ Generating certificates and keys ...
    ▪ Booting up control plane ...
    ▪ Configuring RBAC rules ...
🔎  Verifying Kubernetes components...
    ▪ Using image gcr.io/k8s-minikube/storage-provisioner:v5
🌟  Enabled addons: storage-provisioner, default-storageclass
🏄  Done! kubectl is now configured to use "minikube" cluster and "default" namespace by default
```
Check the minikube cluster:
```bash
❯ kubectl cluster-info
Kubernetes control plane is running at https://127.0.0.1:50457
CoreDNS is running at https://127.0.0.1:50457/api/v1/namespaces/kube-system/services/kube-dns:dns/proxy

To further debug and diagnose cluster problems, use 'kubectl cluster-info dump'.
```
