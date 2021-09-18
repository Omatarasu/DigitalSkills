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


Pods:
---
    kubectl run nginx --image nginx
> run pod with nginx


    kubectl get pods
> look at pods
