# Monitoring

Monitoring with prometheus

Forked with <3 from:

https://devopscube.com/setup-prometheus-monitoring-on-kubernetes/
https://devopscube.com/setup-grafana-kubernetes/
https://devopscube.com/alert-manager-kubernetes-guide/

https://github.com/bibinwilson/kubernetes-prometheus
https://github.com/bibinwilson/kubernetes-grafana
https://github.com/bibinwilson/kubernetes-alert-manager

## Setup

    kubectl apply -f deployments/monitoring/setup/namespace.yaml
    kubectl apply -n monitoring -f deployments/monitoring
    kubectl apply -n monitoring -f deployments/monitoring/grafana
    kubectl apply -n monitoring -f deployments/monitoring/alert-manager

kubectl create ns sentry
helm dependency update
helm install sentry sentry -n sentry -f sentry/values.yaml
