# InfluxDB Kubernetes Deployment

[InfluxDB Container](https://hub.docker.com/_/influxdb)
[InfluxDB Setup CLI Flags](https://docs.influxdata.com/influxdb/v2.0/reference/cli/influx/setup/#flags)

Create Secret

    kubectl create secret -n monitoring generic influxdb-admin --from-literal=ADMIN_PASSWORD=topadmin123!

Deploy

    kubectl apply -n monitoring -f deployments/influxdb
    kubectl wait -l statefulset.kubernetes.io/pod-name=influxdb-0 --for=condition=ready pod --timeout=-1s -n monitoring


    kubectl apply -n monitoring -f deployments/influxdb/setup/setup_job.yaml


    kubectl get service influxdb -n monitoring
    kubectl port-forward service/influxdb 8086 -n monitoring
    http://localhost:8086/signin
Clean up

    kubectl delete -n monitoring -f deployments/influxdb
    kubectl delete -n monitoring -f deployments/influxdb/setup/setup_job.yaml
