# grafana
Grafana helm chart


### Notes
Provider config map:
must have label: app.kubernetes.io/name=grafana
Contains provider.yaml file, which holds information like what folder to be created in grafana, where to put the dashboard json files from json configmap


Dashboard config maps
must have label: grafana_dashboard=testfolder
using this annotation we can specify where the sidecard shoudl keep the dashboard json file: k8s-sidecar-target-directory=/tmp/dashboards/testfolder


kubectl label cm dash4 grafana_dashboard=nginx-ingress-controller
kubectl annotate cm dash4 k8s-sidecar-target-directory=/tmp/dashboards/nginx-ingress-controller