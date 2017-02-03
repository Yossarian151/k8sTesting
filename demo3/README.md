##Demo "Happy Birthday K8s" application. App will show hostname of POD
It's running in.
##Demo App was written in "go" and pushed to docker registry.
###K8s will fetch our "Happy Birthday K8s" application. from docker Registry
#And deploy pod, service, deployment.
#We going to test how Replicaton Controllr puts cluster to desired state.
#Scale Cluster
#Do Rolling Update of new version of the App.

###Create Docker image:
chmod +x ./build.sh
./build.sh
docker build -t archyufa/webk8sbirthday:1.0.4 .
docker push archyufa/webk8sbirthday:1.0.4

#Show configs with 3 replicas.
cat kdemo/kdemo-dep.yaml

###Create Deployment:
### Alternative: kubectl run kdemo --image=archyufa/webk8sbirthday:1.0.3 --port=8080

kubectl create -f kdemo/kdemo-dep.yaml

#Check pods:
kubectl get pods

###Create and than expose a Service:
### Alternative:  kubectl expose deployment/kdemo --type=NodePort
kubectl create -f kdemo/kdemo-svc.yaml



###Find Expose Endpoint:
minikube ip
kubectl get svc kdemo -o wide
kubectl describe svc/kdemo


#Let's see how RC works.

###Second screen
while :; do clear; k get pod; sleep 2; done

#Let's kill 1 container. So that we will have 2 containers
docker ps |

#Let's kill a pod:
kubectl get pods
kubectl delete pod

###Scale
kubectl scale deployment/kdemo --replicas=6
kubectl scale deployment/kdemo --replicas=9
kubectl scale deployment/kdemo --replicas=5

###Rolling Update

kubectl edit deployment/kdemo
Change to (image: archyufa/webk8sbirthday:1.0.4)
### Rollback
kubectl edit deployment/kdemo
kubectl rollout
kubectl rollout undo deployment/kdemo
