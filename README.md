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

## Connect to Prometheus dashboard on http://localhost:9090
```
k port-forward svc/prometheus-kube-prometheus-prometheus 9090 -n monitoring
```

## Connect to Grafana dashboard on http://localhost:8080 ( admin/prom-operator )
```
k port-forward svc/prometheus-grafana 8080:80 -n monitoring
```
