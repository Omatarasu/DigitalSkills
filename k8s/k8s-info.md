master node:
---
#### ETCD
>key-value storage of kubernetis in master node

>listen on port 2379

>etcdctl - command to control it 

#### kube-scheduler
> plans which pod to which node 

#### controller-manager
> node-controller, replication-controller

> monitors the life cycle of pods, nodes and etc.


#### kube-apiserver
> kubectl communicate with it

> provide communication with components of cluster 


#### container engines 
>docekr or another 

worker node:
---
#### kubelet 
>communicate with kube-apiservice for manage containers

#### kube-proxy 
>communication containers on different nodes
>services are part of kube-proxy


#### container engines 
>docekr or another 

Creating Templates:
---
    kubectl create deployment \
    --replicas=3 \
    --image=nginx \
    --dry-run=client \
    nginx-delpoyment \
    -o yaml > \
    deployment-nginx.yaml
Pods:
---
    kubectl run nginx --image nginx
> run pod with nginx


    kubectl get pods
> look at pods

    kubectl create -f pod.yaml
> create pod from yaml file

ReplicaSets:
---
    kubectl apply -f replicaSet.yaml
> apply configuration 

    kubectl edit rs nginx-rs
>edit configuration file  
 
    kubectl scale replicas=5 rs nginx-rs 
>scale pods, change the configuration file
 
> replicaSet include pods config file and section selector

Deloyment:
---
    kubectl apply -f replicaSet.yaml
> same as replicaSet, but in kind: Deployment

Namespaces:
---
    kubectl create ns dev
> create namespace
    
    kubectl get pods -n dev
> run command in another namespace

    kubectl config set-context $(kubectl config current-context) --namespace=dev
> switch namespace

    kubectl get pods --all-namespces
> show pods in all namespaces

 Service:
 ---
type one is NodePort: 
>on each node you can get to the service by port

type two is ClusterIP:
>

yaml files:
---
[pod.yaml](https://github.com/Omatarasu/DigitalSkills/files/7189897/pod.txt)

[replicaSet.yaml](https://github.com/Omatarasu/DigitalSkills/files/7190075/replicaSet.txt)

[service-NodePort.yaml](https://github.com/Omatarasu/DigitalSkills/files/7190562/service-NodePort.txt)
