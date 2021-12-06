# RabbitMQ

https://www.rabbitmq.com/kubernetes/operator/quickstart-operator.html

Deploy CRD

    kubectl apply -f deployments/rabbitmq/crd/cluster-operator.yml
    kubectl delete -f deployments/rabbitmq/crd/cluster-operator.yml

Deploy Cluster

    kubectl apply -f deployments/rabbitmq/rmq-cluster.yaml
    kubectl delete -f deployments/rabbitmq/rmq-cluster.yaml

    username="$(kubectl get secret hello-world-default-user -o jsonpath='{.data.username}' | base64 --decode)"


echo "username: $username"
password="$(kubectl get secret hello-world-default-user -o jsonpath='{.data.password}' | base64 --decode)"
echo "password: $password"

https://github.com/rabbitmq/cluster-operator/blob/main/docs/examples/production-ready/rabbitmq.yaml

default_user_7KCXvhOexgS6sS2lpYg
twyJOemUPlK2DxzbWSSwzydtELe_Mbah