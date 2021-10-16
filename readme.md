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

CJ-Z9PE-D16-SERIES

## Benchmark

    sudo apt install sysbench
    sysbench --test=cpu run

            Threads started!

        CPU speed:
            events per second:   700.36

        General statistics:
            total time:                          10.0010s
            total number of events:              7007

        Latency (ms):
                min:                                    1.41
                avg:                                    1.43
                max:                                    2.99
                95th percentile:                        1.44
                sum:                                 9997.55

        Threads fairness:
            events (avg/stddev):           7007.0000/0.00
            execution time (avg/stddev):   9.9975/0.00

    sysbench --test=memory run
    sysbench --test=fileio --file-test-mode=seqwr run

    ./geekbench4

scp ~/Downloads/phoronix-test-suite_10.6.1_all.deb cj@192.168.1.119:~/Downloads/phoronix-test-suite_10.6.1_all.deb
scp ~/Downloads/Geekbench-5.4.1-Linux.tar.gz cj@192.168.1.119:~/Downloads/Geekbench-5.4.1-Linux.tar.gz

sudo dpkg -i ~/Downloads/phoronix-test-suite_10.6.1_all.deb

phoronix-test-suite list-available-tests

phoronix-test-suite list-recommended-tests

phoronix-test-suite benchmark pts/apache
phoronix-test-suite benchmark pts/compilation
phoronix-test-suite benchmark pts/compiler  
 phoronix-test-suite benchmark pts/chess
phoronix-test-suite benchmark server

phoronix-test-suite benchmark cpu
phoronix-test-suite benchmark memory
phoronix-test-suite benchmark multicore
phoronix-test-suite benchmark server-memory
phoronix-test-suite benchmark server-cpu-tests
phoronix-test-suite benchmark cpu-massive
phoronix-test-suite benchmark network
phoronix-test-suite benchmark server kickinespresso
phoronix-test-suite benchmark pgbench kickinespresso
phoronix-test-suite benchmark build-linux-kernel kickinespresso

         Reference: https://openbenchmarking.org/result/1706268-TR-CPUGOVERN32

https://www.smartystreets.com/blog/2015/10/performance-testing-with-phoronix/

phoronix-test-suite batch-benchmark pts/cpu
phoronix-test-suite benchmark build-linux-kernel

sudo apt-get install hardinfo
phoronix-test-suite system-sensors
phoronix-test-suite benchmark webp

          Reference: https://openbenchmarking.org/result/1706268-TR-CPUGOVERN32

https://cheatsheet.dennyzhang.com/cheatsheet-minikube-a4

sudo microk8s status --wait-ready
microk8s enable dashboard dns registry istio
microk8s enable prometheus storage
microk8s config
microk8s kubectl get nodes

token=$(microk8s kubectl -n kube-system get secret | grep default-token | cut -d " " -f1)
microk8s kubectl -n kube-system describe secret $token
microk8s kubectl port-forward -n kube-system service/kubernetes-dashboard 10443:443
