# Zipkin

[Zipkin](https://zipkin.io/)

## Deployment

    kubectl apply -n monitoring -f deployments/zipkin

## Cluster Access

    ZIPKIN_URL: http://zipkin.monitoring.svc.cluster.local:9411/api/v2/spans

    