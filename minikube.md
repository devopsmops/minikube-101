# Minikube - Запуск кластера

Присоединяйтесь к нам - [Youtube](https://www.youtube.com/channel/UCqC3c7UHtwoX2wy7fdHc6gg) и [Telegram](https://t.me/devops_mops)
<br><br>

Запуск и остановка Minikube
```
minikube start
minikube stop
```
<br>

Запустить кластер из трех узлов
```
minikube start --nodes 3
```

Добавить узел в кластер
```
minikube node add
```
<br>

Управление узлами кластера
```
minikube node list
minikube node stop <k8s_node_name>
minikube node start <k8s_node_name>
minikube node delete <k8s_node_name>
```
<br>

Выполнить вход по ssh на виртуальную машину Minikube
```
minikube ssh
```
<br>

Удалить кластер Minikube
```
minikube delete
```
<br>

Запуск Minikube с определенной версией Kubernetes
> Поддерживается последняя версия Kubernetes и 6 предыдущих версий
```
minikube start --kubernetes-version=v1.20.2
```
<br>

Запуск Minikube с указанием Container runtime 
> Container runtime по умолчанию - Docker
```
minikube start --container-runtime=docker
minikube start --container-runtime=cri-o
minikube start --container-runtime=containerd
```
<br>

Запустить узлы кластера как виртуальные машины
> По умолчанию запускаются в Docker (Docker in Docker)
```
minikube start --driver=virtualbox
```
<br>

Указать конфигурацию узлов при запуске
> Не забывайте про ограничение ресурсов, которое устанавливается в Docker Desktop, если выбран --driver=docker
```
minikube start --cpus=2 --memory='4000mb' --disk-size='20000mb'
```