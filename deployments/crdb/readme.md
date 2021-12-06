# CoachRoachDB

Deploy Operator

    kubectl apply -f deployments/crdb/crd/crd.yaml
    kubectl delete -f deployments/crdb/crd/crd.yaml

Deploy Cluster        

    kubectl apply -f deployments/crdb/crdb-cluster.yaml
    kubectl delete -f deployments/crdb/crdb-cluster.yaml
