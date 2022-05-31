## Understand Kubernetes Buzzword (Day1)

There are a couple of buzzword in Kubernetes which makes our learning a bit hard. In this article I want to explain these terms which are important for us to understand what is Kubernetes.


- Node
- Cluster
- Pod
- Deployment
- Service


## 1. What is Node ?

Node is worker machine which is basically a physical machine, ie., your laptop. It can also be a virtual machine.
> Node : worker machine / physical machine / virtual machine


## 2. What is Cluster?
Cluster consists of multiple nodes. We just understand that node is a worker machine, so we can think cluster as a group of worker machines.

> Cluster: multiple nodes

## 3. What is Pod?
Pod exits in the node and it is the smallest deployable object in Kubernetes. Each pod can contain one or more containers with shared storage and network resources. Pod is usually a 1-1 mapping with containers. If we want to scale up our application, we can add more pods. Likewise, we can delete existing pods to scale down the application.

## 4. What is Deployment?
The deployment is a kubernetes object which has a higher hierarchy, the deployment will provide us with the capacity to upgrade the underlying instances seamlessly using rolling updates,undo changes and pause and resume changes as required. So Kubernetes deployment is used to tell Kubernetes to create or modify pods which consists containers.

## 5. What is Service ?

A service is responsible for enabling network access to a set of pods by assigning a name and unique IP address. You can think Kubernetes Service as a laser pen points to the pod which has a certain label. It is a abstract concept. There are mainly three types of kubernetes service.These are ClusterIP, NodePort and LoadBalancer.  The default service type is ClusterIP.  The smallest exposure is ClusterIp which just expose the service within the K8s cluster.  The NodePort will expose a service via a static port on each node's ip while LoadBalancer will expose the service via the cloud providers's load balancer.

So based on the exposure level:
ClusterIp < NodePort < LoadBalancer.

Here is the useful link for reference.
[Differences between ClusterIp, NodePort and LoadBalancer](https://stackoverflow.com/questions/41509439/whats-the-difference-between-clusterip-nodeport-and-loadbalancer-service-types)


