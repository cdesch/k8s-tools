# digitial ocean deployments

## Deploy

    kubectl apply -f deployments/do/first_service.yaml
    kubectl delete -f deployments/do/first_service.yaml

    kubectl apply -f deployments/do/ingress.yaml
    kubectl delete -f deployments/do/ingress.yaml

## Ingress

Get ingress

    kubectl get svc --namespace=ingress-nginx

## Monitoring

    kubectl port-forward svc/kube-prometheus-stack-grafana 8080:80 -n kube-prometheus-stack

    http://localhost:8080.

    Username: admin
    Password: prom-operator