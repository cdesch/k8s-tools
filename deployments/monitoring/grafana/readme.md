# Grafana Cheat Sheet

https://banzaicloud.com/blog/grafana-templating/
https://medium.com/@amimahloof/kubernetes-promql-prometheus-cpu-aggregation-walkthrough-2c6fd2f941eb
https://promlabs.com/promql-cheat-sheet/
https://blog.ruanbekker.com/cheatsheets/grafana/#prometheus-datasource
https://lzone.de/cheat-sheet/Prometheus
https://ryanharrison.co.uk/2021/04/05/prometheus-monitoring-cheat-sheet.html

## Variable Definition

$Node       label_values(kubernetes_io_hostname)
$Pod label_values(kube_pod_info, pod)
$Pod_ip     label_values(kube_pod_info, pod_ip)
$phase label_values(kube_pod_status_phase, phase)
$container label_values(kube_pod_container_info, container)

label_values(kube_pod_info{namespace=~"$namespace"},pod)
label_values(kube_pod_info{namespace="$namespace"},pod)
namespace="$namespace", instance=~"$pod"}
label_values(kube_namespace_labels, namespace)

kube_alive_pods = kube_pod_status_phase{pod=~"frontend-.\*",phase="Running"} == 1

label_values(kube_alive_pods, pod)

1$container	label_values(kube_pod_container_info{pod="$Pod"}, container)

## Dashboards

    https://grafana.com/grafana/dashboards/11674
    https://grafana.com/grafana/dashboards/6876
    https://grafana.com/grafana/dashboards/315
