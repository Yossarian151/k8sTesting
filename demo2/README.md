IN THIS DEMO WE DEMONSTRATE PODs functionality
How you can start the pod using YAML and CLI.
1) We launch ngimx  docker container on K8s with Kubectl.

#Launch a single docker container:
kubectl run nginxv1 --image=nginx:1.10.0

#Get pods
kubectl get pods



1) We launch nginx  docker container on K8s with Kubectl.

!!!! Kubernetes supports two different file formats YAML and JSON. Each format can describe the same function of K8s:

#Another way. Using a Yaml file:
#Create a Container usimg YAML file
#Chek config file
cat pods/monolith.yaml


#Create the monolith pod
kubectl create -f pods/monolith.yaml


#Examine pods
kubectl get pods

#Info about the Pod. And troubleshooting:
kubectl describe pods monolith


###Pods allocated private IP by default, it can not reach outside of  the
cluster
#Set up port-forwarding
kubectl port-forward monolith 10080:80

#Check if App is working:
curl http://127.0.0.1:10080

It works!

#In Case need to troubleshoot:
kubectl exec monolith --stdin --tty -c monolith /bin/sh

# Check Dasboard View

#Delete Pods
kubectl delete
