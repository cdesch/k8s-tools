# CoachRoachDB

Deploy Operator

    kubectl apply -f deployments/crdb/crd/crd.yaml
    kubectl apply -f deployments/crdb/crd/operator.yaml

    kubectl delete -f deployments/crdb/crd/crd.yaml
    kubectl delete -f deployments/crdb/crd/operator.yaml

Deploy Cluster



    kubectl apply -f deployments/crdb/crdb-cluster-small.yaml
    kubectl delete -f deployments/crdb/crdb-cluster-small.yaml

    kubectl apply -f deployments/crdb/crdb-cluster-prod.yaml
    kubectl delete -f deployments/crdb/crdb-cluster-prod.yaml

    kubectl apply -f deployments/crdb/secure-client.yaml
    kubectl delete -f deployments/crdb/secure-client.yaml

Clean Up (Destroy All)

    kubectl delete -f deployments/crdb
    kubectl delete -f deployments/crdb/crd

Terminal into Secure Client to Create Permissions

    kubectl exec -it cockroachdb-client-secure \
    -- ./cockroach sql \
    --certs-dir=/cockroach/cockroach-certs \
    --host=cockroachdb-public

    CREATE USER roach WITH PASSWORD 'Q7gc8rEdS';
    CREATE USER developer WITH PASSWORD 'password';

    GRANT admin TO roach;
    GRANT admin TO developer;

Check

    kubectl get pods

cockroachdb-public

## Access Console

    kubectl port-forward service/cockroachdb-public 8080

http://localhost:8080