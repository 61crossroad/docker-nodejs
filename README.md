# Minikube, docker, node.js deployment
## install minikube
- brew install minikube
- minikube start
## deploy
- kubectl cluster-info
- kubectl get nodes
- kubectl run kubia --image=freestic/kubia --port=8080
- kubectl get pods
## create load balancer
- kubectl expose po kubia --type=NodePort --port=8080 --name kubia-http
- kubectl get svc
- minikube service kubia-http --url

## get the port and access
- ps -ef | grep docker@127.0.0.1
- curl 127.0.0.1:{NODE_PORT}

https://minikube.sigs.k8s.io/docs/handbook/accessing/
