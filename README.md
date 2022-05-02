## k8s commands

### get nodes status
kubectl get nodes

### get pods status
kubectl get pods

### get services status
kubectl get services

### create deployments
kubectl create deployment nginx-deployment --image=nginx

### list deployments
kubectl get deployment

### list replicaset
kubectl get replicaset

### edit deployment
kubectl edit deployment nginx-deployment

### display log for pod
kubectl logs mongodb-deployment-7495897c64-d6vxl

### describe pods
kubectl describe pod mongodb-deployment-7495897c64-d6vxl

### interactive shell to pod
kubectl exec -it mongodb-deployment-7495897c64-d6vxl -- bin/bash

### delete deployment
kubectl delete deployment mongodb-deployment

### apply config
kubectl apply -f nginx-deployment.yaml 

### delete config
kubectl delete -f nginx-deployment.yaml 

### apply mutiple config files
kubectl apply -f .

### describe service
kubectl describe service nginx-service

### get wide status
kubectl get pods -o wide

### get 3rd part (status) in k8s config
kubectl get deployment nginx-deployment -o yaml

### delete mutiple config files
kubectl delete -f .

### get all k8s components
kubectl get all

### get k8s components in watch mode
kubectl get pods --watch

### get cluster information
kubectl cluster-info

### create namespace
kubectl create namespace my-namespace

### change active namespace (must be install kubens)
kubens [target-namespace]

### get k8s service endpoints
kubectl get endpoints

### minikube install ingress
minikube addons enable ingress 

### describe ingress
kubectl describe ingress dashboard-ingress -n kubernetes-dashboard

### using helm to install helm charts
helm install mongodb --values mongo-lke.yaml bitnami/mongodb

### using helm to install nginx-ingress
helm install nginx-ingress nginx-stable/nginx-ingress --set controller.publishService.enable=true

### scale replicas
kubectl scale --replicas=0 statefulset/mongodb

### list helm charts
helm ls

### uninstall helm charts
helm uninstall mongodb

### k9s cli
k9s

### create secret from file / create docker login credentials from file
kubectl create secret generic my-secret --from-file=.dockerconfigjson=.docker/config.json --type=kubernetes.io/dockerconfigjson

### create docker login credentials from kubectl
kubectl create secret docker-registry my-registry-key --docker-server=[rep-url] --docker-username=[username] --docker-password=[password]
