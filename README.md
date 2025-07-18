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

- kubectl installed and configured ([https://youtu.be/IBkU4dghY0Y](https://youtu.be/IBkU4dghY0Y))
- Helm installed: ([https://kubernetestraining.io/blog/installing-helm-on-mac-and-windows](https://kubernetestraining.io/blog/installing-helm-on-mac-and-windows))
