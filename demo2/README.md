# Demo1: Demonstrating how you can start the pod using YAML and CLI.

## Launch nginx  docker container on K8s with kubectl

1. Launch a single docker container:
`kubectl run nginxv1 --image=nginx:1.10.0`

2. Get pods
`kubectl get pods`

## Launch nginx docker container on K8s with manifest (YAML or JSON).

1. Chek config file
`cat pods/monolith.yaml`

2. Create the monolith pod
`kubectl create -f pods/monolith.yaml`

3. Examine pods
`kubectl get pods`

4. Info about the Pod. And troubleshooting:
`kubectl describe pods monolith`

## Exposing Pods without services

Pods allocated private IP by default, it can not reach outside of  the cluster

1. Set up port-forwarding
`kubectl port-forward monolith 10080:80`

2. Check if App is working:
`curl http://127.0.0.1:10080`

**It works!**

## Troubleshooting
`kubectl exec monolith --stdin --tty -c monolith /bin/sh`

##Delete Pods
`kubectl delete`
