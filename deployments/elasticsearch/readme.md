# ElasticSearch

https://www.elastic.co/guide/en/cloud-on-k8s/current/k8s-deploy-eck.html

## Deploy the Operator

    kubectl create -f https://download.elastic.co/downloads/eck/1.8.0/crds.yaml
    kubectl apply -f https://download.elastic.co/downloads/eck/1.8.0/operator.yaml

    kubectl create -f deployments/elasticsearch/crds.yaml
    kubectl apply -f deployments/elasticsearch/operator.yaml

Monitor Logs 

    kubectl -n elastic-system logs -f statefulset.apps/elastic-operator

Deploy Cluster

    kubectl apply -f deployments/elasticsearch/elastic-cluster.yaml
    kubectl apply -f deployments/elasticsearch/kibana.yaml

Port forward Kibana

    kubectl port-forward service/quickstart-kb-http 5601


    kubectl get secret quickstart-es-elastic-user -o=jsonpath='{.data.elastic}' | base64 --decode; echo


    Username: elastic
    kubectl get secret quickstart-es-elastic-user -o=jsonpath='{.data.  elastic}' | base64 --decode; echo

    https://localhost:5601