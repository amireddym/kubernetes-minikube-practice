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

kubectl api-resources --namespaced=false
kubectl api-resources --namespaced=true

kubectl get configmap -n default
kubectl apply -f filePath --namespace=my-namespace

brew install kubectx
kubens
kubens my-namespace

minikube addons enable ingress   --- might not work

minikube dashboard --url

#HELM CHART

its a directory structure for yaml files
my-chart/ 
    Chart.yaml  -- metadata
    values.yaml  -- template data values which are default can be override
    charts/   -- dependent charts
    templates/  -- template files location

helm install --values=new-values.yaml <chartName>
.Values object is created by merging values.yaml and new-values.yaml to create that object to use in Template files

helm install --set version=2.0.0   -- setting from cli the values to override default ones
helm upgrade <chartName>   to update the charts on cluster
helm rollback <chartName>

client  -> server (Tiller) -> k8 cluster

Volumes in kubernetes
Persistent Volumes  --- not namespaced, Accessible for whole cluster
Persistent Volume Claim  --- pods access storage by claiming the volume. volume claim then finds the appropriate one from the persistent volumes. Claims should be in the same namespace as the pods using them.
Storage Class

kubectl get endpoints
Headless Services --- cluserIP to None

helm repo add bitnami <repoUrl>
helm install my-release bitnami/wordpress
helm search hub wordpress
helm search hub wordpress

helm list
helm uninstall my-release
helm repo update
