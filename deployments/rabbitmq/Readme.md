# RabbitMQ

https://www.rabbitmq.com/kubernetes/operator/quickstart-operator.html

Deploy CRD

    kubectl apply -f deployments/rabbitmq/crd/cluster-operator.yml
    kubectl delete -f deployments/rabbitmq/crd/cluster-operator.yml

Deploy Cluster

    kubectl apply -f deployments/rabbitmq/rmq-cluster-local.yaml
    kubectl delete -f deployments/rabbitmq/rmq-cluster-local.yaml

    username="$(kubectl get secret hello-world-default-user -o jsonpath='{.data.username}' | base64 --decode)"


    echo "username: $username"
    password="$(kubectl get secret hello-world-default-user -o jsonpath='{.data.password}' | base64 --decode)"
    echo "password: $password"

https://github.com/rabbitmq/cluster-operator/blob/main/docs/examples/production-ready/rabbitmq.yaml

    kubectl -n default port-forward "service/hello-world" 15672 5672
    http://localhost:15672

    kubectl -n default port-forward "service/hello-world" 8081:15672 5672
    http://localhost:8081

    kubectl get -o yaml configmap hello-world-server-conf
