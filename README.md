# Kubernetes Distributed Tracing with Tempo, Alloy and Grafana

# Viewing Traces in Grafana

1. From the Grafana homepage (localhost:3000):

2. Select the Tempo data source

3. Go to the Explore tab

4. Make sure "Search" is selected as the query type

5. Click "Run query"

# Helm Repositories for Loki, Prometheus, Grafana

- Loki Helm Repository: https://grafana.github.io/helm-charts/
- Loki values.yaml: https://github.com/grafana/loki/blob/main/production/helm/loki/values.yaml
- Prometheus Helm Repository: https://prometheus-community.github.io/helm-charts
- Prometheus values.yaml: https://github.com/prometheus-community/helm-charts/blob/main/charts/kube-prometheus-stack/values.yaml

## Installing tempo

```bash
helm install loki grafana/tempo --values tempo-values.yml  --version 6.29.0 --namespace monitoring

```

## Installing kube-prometheus-stack

Installing kube-prometheus-stack if custom-values.yaml file isn't present. This adds loki as an additional data source.

```bash
helm install prometheus prometheus-community/kube-prometheus-stack --version 45.7.1 \
  --namespace monitoring \
  --values prometheus-stack-values.yml
```

### Testing Prometheus

port-forward

```bash
kubectl port-forward -n monitoring svc/prometheus-operated 9090:9090
```

### Testing Grafana

Access grafana password

```bash
kubectl get secret -n monitoring prometheus-grafana -o jsonpath="{.data.admin-password}" | base64 --decode
```

port-forward

```bash
kubectl port-forward -n monitoring svc/grafana 3000:80
```
