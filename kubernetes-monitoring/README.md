# Репозиторий для выполнения домашних заданий курса "Инфраструктурная платформа на основе Kubernetes-2024-10" 

#### Установим ingress controller:
```bash
minikube addons enable ingress
```

#### Установим kube-prometheus-stack через helm:
https://github.com/prometheus-operator/prometheus-operator/blob/main/Documentation/installation.md#install-using-helm-chart \
https://github.com/prometheus-community/helm-charts/tree/main/charts/kube-prometheus-stack \
```bash
helm install prom prometheus-community/kube-prometheus-stack -f ./prometheus/prometheus.yaml --atomic
```
```
NAME: prom
LAST DEPLOYED: Thu Jan  2 20:10:21 2025
NAMESPACE: default
STATUS: deployed
REVISION: 1
NOTES:
kube-prometheus-stack has been installed. Check its status by running:
  kubectl --namespace default get pods -l "release=prom"

Visit https://github.com/prometheus-operator/kube-prometheus for instructions on how to create & configure Alertmanager and Prometheus instances using the Operator.
```
![Продеплоен kube-prometheus-stack](../images/kubernetes-monitoring/kube-prometheus-stack__installed.jpg)

#### Применим манифесты
```bash
kubectl apply -f ./namespace.yaml
kubectl apply -f ./
```
```
configmap/hw-configmap-nginx unchanged
deployment.apps/hw-deployment created
servicemonitor.monitoring.coreos.com/nginx-metrics configured
service/hw-service configured

```
#### Проверяем установку прометеус:
```
kubectl port-forward service/prom-kube-prometheus-stack-prometheus 9090:9090
```
Prometheus UI открывается на http://localhost:9090 \
Проверяем, что в  Status -> Target health -> ServiceMonitor/homework/nginx-metrix/0: `UP` \
![Prometheus hw-service health](../images/kubernetes-monitoring/prometheus__hw-service__health.jpg)
Видим доступные метрики: \
![Prometheus hw-service metrics](../images/kubernetes-monitoring/prometheus__hw-service__metrics.jpg)
Запрашиваем метрику nginx_up в Prometheus UI: \
![Prometheus hw-service nginx_up](../images/kubernetes-monitoring/prometheus__hw-service__metric_nginx_up.jpg)
Запрашиваем метрику nginx_up через CURL: \
![Prometheus hw-service nginx_up](../images/kubernetes-monitoring/prometheus__hw-service__metric_nginx_up__CURL.jpg)

#### Проверяем установку графаны:
```
kubectl port-forward service/prom-grafana  3000:80
```
Grafana UI открывается на http://localhost:3000 \
Логин / пароль: `admin / prom-operator` \
В Grafana сконфигурирован Prometheus datasource слушающий на порту 9090 prom-kube-prometheus-stack-prometheus
![Grafana hw-service nginx_up](../images/kubernetes-monitoring/grafana__prometheus_datasources.jpg)
Метрика nginx_up в Grafana на дашбоарде на основе Prometheus datasource
![Grafana hw-service nginx_up](../images/kubernetes-monitoring/grafana__hw-service__metric_nginx_up.jpg)