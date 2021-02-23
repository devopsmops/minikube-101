# Minikube - Тестирование различных Container runtime

Присоединяйтесь к нам - [Youtube](https://www.youtube.com/channel/UCqC3c7UHtwoX2wy7fdHc6gg) и [Telegram](https://t.me/devops_mops)
<br><br>

## Docker
Запускаем Minikube c Docker
```
minikube start --kubernetes-version v1.20.2 --container-runtime=docker
```
<br>

Проверяем, что кластер создан и Container runtime - Docker
```
kubectl get no -o=custom-columns=NAME:.metadata.name,CONTAINER-RUNTIME:.status.nodeInfo.containerRuntimeVersion
```
<br>

Вывести список запущенных контейнеров
```
sudo docker ps
```
<br>

```
sudo runc --root /run/docker/runtime-runc/moby list
```
<br>

```
sudo crictl ps
```
<br>

## Containerd
Запускаем Minikube c Containerd
```
minikube start --kubernetes-version v1.20.2 --container-runtime=containerd
```
<br>

```
sudo runc --root /run/containerd/runc/k8s.io list
```
<br>

```
sudo crictl ps
```
<br>

sudo crictl info

## CRI-O
Запускаем Minikube c CRI-O
```
minikube start --kubernetes-version v1.20.2 --container-runtime=cri-o
```
<br>

```
sudo runc list
```
<br>

```
sudo crictl ps
```
<br>

```
podman ps --sync --external --all
```
<br>

sudo crictl info