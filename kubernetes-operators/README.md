# Репозиторий для выполнения домашних заданий курса "Инфраструктурная платформа на основе Kubernetes-2024-10" 


#### Применим манифесты
```bash
kubectl apply -f ./
```

#### Проверяем что все ресурсы созданы и в частности pod MySQL и persistent volume для него
Консоль - ресурсы созданы:
![Консоль - ресурсы созданы](../images/kubernetes-operators/resources_created.jpg)
Lens - deployment:
![Lens - deployment](../images/kubernetes-operators/deployment_created.jpg)
Lens - pods:
![Lens - pods](../images/kubernetes-operators/pods_created.jpg)
Lens - persistent volume:
![Lens - persistent volume](../images/kubernetes-operators/PV.jpg)
Lens - persistent volume claim:
![Lens - persistent volume claim](../images/kubernetes-operators/PVC.jpg)
Lens - custom resource definition:
![Lens - custom resource definition](../images/kubernetes-operators/CRD.jpg)
Lens - custom resource:
![Lens - custom resource](../images/kubernetes-operators/CR.jpg)
Lens - service account:
![Lens - service account](../images/kubernetes-operators/SA.jpg)
Lens - cluster role:
![Lens - cluster role](../images/kubernetes-operators/cluster_role.jpg)
Lens - cluster role binding:
![Lens - cluster role binding](../images/kubernetes-operators/cluster_role_binding.jpg)
Lens - replica sets:
![Lens - replica sets](../images/kubernetes-operators/replica_sets.jpg)
Lens - service:
![Lens - service](../images/kubernetes-operators/service.jpg)
Lens - endpoint:
![Lens - endpoint](../images/kubernetes-operators/endpoint.jpg)