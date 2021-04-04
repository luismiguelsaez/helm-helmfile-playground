# helm-helmfile-playground

## Requisites

- Install helm version from 3.x
- Install helm `diff` plugin
```
helm plugin install https://github.com/databus23/helm-diff
```
- Kubernetes cluster running, for example kind local cluster
```
kind create cluster --config kind/ingress-enabled.yaml --name testing
```

## Deploy stack
```
helmfile sync
```

## Check Prometheus current configuration
Checking the `Prometheus`object, you can review the `serviceMonitor` and `rulesSelector`:
```
k get prometheus prometheus-kube-prometheus-prometheus -oyaml -n monitoring
```

## Connect to Prometheus dashboard
```
k port-forward svc/prometheus-kube-prometheus-prometheus 9090 -n monitoring
```
