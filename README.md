# Simple LB
Operator that allows you to use [Kubernetes LoadBalancer Service](https://kubernetes.io/docs/concepts/services-networking/service/#loadbalancer) type on non-public cloud, by exposing ports on nodes with `simplelb.amurant.io/enablelb=true` label.

## Howto use?
### Label nodes
```
kubectl label <node name> simplelb.amurant.io/enablelb=true
kubectl get nodes --show-labels
```
### Deploy operator
```
kubectl create -f simplelb/deploy
```
### Deploy example app (optional)
```
kubectl create deployment hello-node --image=gcr.io/hello-minikube-zero-install/hello-node

kubectl expose deployment hello-node --type=LoadBalancer --port=8080
```

## Inspired by
 - https://github.com/kontena/akrobateo
 - https://github.com/rancher/k3s/blob/master/pkg/servicelb/controller.go
