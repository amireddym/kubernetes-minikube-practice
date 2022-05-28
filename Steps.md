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

kubectl apply -f <filepath>
kubectl delete -f <filepath>

Kubernetes config file Structure
1. Metadata
2. Specification
3. Status --- generated automatically by kubernetes

Labels and Selectors
Metadata --- labels
Spec --- Selectors

kubectl describe service nginx-service
kubectl get pod -o wide
kubectl get deployment nginx-server -o yaml

kubectl get all

echo -n 'plainText' | base64

kubectl get secret
minikube service mongo-express-service --url

kubectl get namespaces
kubectl cluster-info

kubectl create namespace my-namespace
