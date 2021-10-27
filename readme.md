# k8s-tools

## Dashboard

https://artifacthub.io/packages/helm/k8s-dashboard/kubernetes-dashboard
helm repo add kubernetes-dashboard https://kubernetes.github.io/dashboard/
helm install kubernetes-dashboard kubernetes-dashboard/kubernetes-dashboard
helm uninstall kubernetes-dashboard

https://github.com/kubernetes/dashboard

kubectl apply -f https://raw.githubusercontent.com/kubernetes/dashboard/v2.3.1/aio/deploy/recommended.yaml
kubectl delete -f https://raw.githubusercontent.com/kubernetes/dashboard/v2.3.1/aio/deploy/recommended.yaml
kubectl proxy
http://localhost:8001/api/v1/namespaces/kubernetes-dashboard/services/https:kubernetes-dashboard:/proxy/

    kubectl config get-contexts
    kubectl config use-context docker-desktop
    kubectl config use-context microk8s

## MiniKube

    minikube start
    minikube stop
    minikube pause
    minikube unpause
    minikube dashboard

## [Kube State Metrics](https://github.com/kubernetes/kube-state-metrics)

Deploy Kube State Metrics

    kubectl apply -n kube-system -f deployments/kube-state-metrics
    kubectl delete -n kube-system -f deployments/kube-state-metrics

## MiniKube

    https://minikube.sigs.k8s.io/docs/start/


    minikube config set memory 4096

    minikube config view

## Ingress

https://minikube.sigs.k8s.io/docs/handbook/addons/ingress-dns/

https://cheatsheet.dennyzhang.com/cheatsheet-minikube-a4

sudo microk8s status --wait-ready
microk8s enable dashboard dns registry istio
microk8s enable prometheus storage
microk8s config
microk8s kubectl get nodes

token=$(microk8s kubectl -n kube-system get secret | grep default-token | cut -d " " -f1)
microk8s kubectl -n kube-system describe secret $token
microk8s kubectl port-forward -n kube-system service/kubernetes-dashboard 10443:443

kubectl config view

https://medium.com/starschema-blog/monitor-your-infrastructure-with-influxdb-and-grafana-on-kubernetes-a299a0afe3d2

[Awesome Kubernetes](https://github.com/ramitsurana/awesome-kubernetes)
[RBAC Manager](https://github.com/FairwindsOps/rbac-manager)
[KubeMonkey](https://github.com/asobti/kube-monkey)
[KubeBench](https://github.com/aquasecurity/kube-bench)
[Kubeadm](https://github.com/kubernetes/kubeadm)
[Falco](https://falco.org/)
[kubetools](https://collabnix.github.io/kubetools/)
[OperatorHub](https://operatorhub.io/)
[K8s Operators](https://www.replex.io/blog/10-kubernetes-operators-every-devops-needs-to-know-about)


Ubunutu Disable GUI

    https://linuxconfig.org/how-to-disable-enable-gui-on-boot-in-ubuntu-20-04-focal-fossa-linux-desktop


pod gracefulshutdown
https://pracucci.com/graceful-shutdown-of-kubernetes-pods.html