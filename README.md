# helm-helmfile-playground

## Requisites

- Install helm version from 3.x
- Install helm `diff` plugin
```
helm plugin install https://github.com/databus23/helm-diff
```
- Kubernetes cluster running, for example kind local cluster
```
kind create cluster --name testing
```

## Deploy stack
```
helmfile sync
```

## Connect to Prometheus dashboard
```
k port-forward svc/prometheus-kube-prometheus-prometheus 9090 -n monitoring
```
