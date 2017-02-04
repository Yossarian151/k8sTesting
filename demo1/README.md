# Minikube

## Deploy Minikube

**Source link:** https://github.com/kubernetes/minikube
Minikube runs a single-node Kubernetes cluster inside a VM on your laptop for users looking to try out Kubernetes or
develop with it day-to-day.

1. Install Minkube OSX:

`curl -Lo minikube
https://storage.googleapis.com/minikube/releases/v0.16.0/minikube-darwin-amd64
&& chmod +x minikube && sudo mv minikube /usr/local/bin/`

2. Install Kubectl linux/amd64
`curl -LO https://storage.googleapis.com/kubernetes-release/release/$(curl -s
https://storage.googleapis.com/kubernetes-release/release/stable.txt)/bin/darwin/amd64/kubectl`


## Demo:

1. Options you have:
`minikube`

2. Let's Start local k8s Cluster.
`minikube start`

3. Meanwhile let's check if we have docker engine installed locally:
`docker version
`docker pull nginx:1.10.0`
`docker run -d --name dockerdemo nginx:1.10.0`
`docker ps`

4. Back to Cluster:
`minikube status
eval $(minikube docker-env)`

5. Check what is running in Minikube
`docker ps`


6. Let's check a Version of K8s
`minikube get-k8s-versions`


# Deploye Demo K8s cluster on GKE
## Google Cloud Platform account setup
* Navigate to https://console.cloud.google.com and login with your
* credentials.
* Select your project from the project listing.

```
gcloud config set compute/zone europe-west1-b
gcloud container clusters create myk8scluster --num-nodes 3
```
# Deploy Demo K8s on Openstack with  Murano K8s
Following the link:
https://content.mirantis.com/rs/451-RBY-185/images/Kubernetes%20on%20OpenStack%20eBook%20Final.pdf

# Magnum 

(WIP)


# Kubeadm
(WIP)


# Kargo

(WIP)

# KOPs 

(WIP)