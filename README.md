# Electricitymap Prometheus Exporter

Exporter to create carbon intensity metric for France in Prometheus ⚡️🌱

It uses the [electricitymap api](https://app.electricitymaps.com/).

The api token is expected in the `AUTH_TOKEN` env variable.

## Build image

```bash
docker build -t electricitymap_exporter:latest .
```

## Deploy in Kubernetes

```bash
kubectl create namespace observability
kubectl create secret -n observability generic electricitymap-exporter-secret --from-literal=AUTH_TOKEN=<token>
kubectl apply -f electricitymap_exporter/kube.yaml
```

## Metric

The `carbon_intensity_fr` should be available in Prometheus.
