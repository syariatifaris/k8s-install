## Kubernetes Cluster Setup

### Install Requirements

Run:
```
sh k8s-install.sh
```

### Init Kubeadm

Run
```
sh kubeadm-init.sh
```

After kubeadm has been initialized successfully, make sure to follow the step which has been stated on the console snippet.

I.E
```
sudo cp /etc/kubernetes/admin.conf $HOME/
sudo chown $(id -u):$(id -g) $HOME/admin.conf
export KUBECONFIG=$HOME/admin.conf
```

Also, we need to setting up master DNS

```
kubectl apply --filename https://git.io/weave-kube-1.6
```

**Validate the master running**
```
kubectl get nodes
```

### Reset Kubeadm

Run
```
sh kubeadm-reset.sh
```