1. Deploy Minikube: (AKA Docker-machine like experience) ALL-IN-ONE

https://github.com/kubernetes/minikube
Run  k8s localy. Minikube runs a single-node Kubernetes
cluster inside a VM on your laptop for users looking to try out Kubernetes or
develop with it day-to-day.

# Install Minkube OSX:
curl -Lo minikube
https://storage.googleapis.com/minikube/releases/v0.6.0/minikube-darwin-amd64
&& chmod +x minikube && sudo mv minikube /usr/local/bin/

# Install Kubectl linux/amd64
curl -Lo kubectl
http://storage.googleapis.com/kubernetes-release/release/v1.3.0/bin/linux/amd64/kubectl
&& chmod +x kubectl && sudo mv kubectl /usr/local/bin/

Demo:
#Options you have:
minikube


#Let's Start local k8s Cluster.
minikube start

#Meanwhile let's check if we have docker engine installed locally:
docker version
docker pull nginx:1.10.0
docker run -d --name dockerdemo nginx:1.10.0
docker ps


Back to Cluster:
minikube status
eval $(minikube docker-env)


#W/A for 1.12
export DOCKER_API_VERSION=1.23

#Check what is running in Minikube
docker ps

#VM in VirtualBox

#Let's check a Version of K8s
minikube get-k8s-versions

#Demo kubectl
#Show Dashboard;
Start nginx app.


2. Deploye Demo K8s cluster on GKE
#### Google Cloud Platform account setup
* Navigate to https://console.cloud.google.com and login with your
* credentials.
* Select your project from the project listing.

```
gcloud config set compute/zone europe-west1-b
gcloud container clusters create myk8scluster --num-nodes 3
```
3. Deploy Demo K8s on Openstack with  Murano K8s
Following the link:
https://content.mirantis.com/rs/451-RBY-185/images/Kubernetes%20on%20OpenStack%20eBook%20Final.pdf

4. Magnum (WIP)

5. Kubeadm (WIP)

6. Kargo (WIP)

7. KOPs 
