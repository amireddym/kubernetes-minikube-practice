#Steps to run Minikube 

minikube start --vm-driver=hyperkit
kubectl get nodes
minikube status

kubectl version
kubectl version --short

kubectl get nodes
kubectl get pod
kubectl get services

kubectl create deployment nginx-server --image=nginx
kubectl get deployment
kubectl get pod
kubectl get replicaset

pod name format --- <deploymentName>+<replicaSetHash>+<podId>
kubectl edit deployment nginx-server

kubectl logs <pod name>
kubectl describe pod <pod name>

kubectl exec -it <pod name> -- bin/bash

kubectl delete deployment nginx-server
kubectl get replicaset
kubectl get pod

