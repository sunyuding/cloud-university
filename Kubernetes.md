# Kubernetes
## Microservice
**Microservices** can be deployed individually on separate servers provisioned with fewer resources - only what is required by each service and the host system itself.

Microservices-based architecture is aligned with **Event-driven Architecture** and **Service-Oriented Architecture (SOA)** principles, where complex applications are composed of small independent processes which communicate with each other through APIs over a network.

## What Is Container Orchestration?
**Container orchestrators** are tools which group systems together to form clusters where containers' deployment and management is automated at scale while meeting the requirements mentioned above.

[Kubernetes]() is an open source orchestration tool, started by Google, part of the [Cloud Native Computing Foundation]() (CNCF) project.

## What Is Kubernetes?
According to the [Kubernetes website](),
```
"Kubernetes is an open-source system for automating deployment, scaling, and management of containerized applications."
```

Kubernetes comes from the Greek word κυβερνήτης, which means helmsman or ship pilot. With this analogy in mind, we can think of Kubernetes as the pilot on a ship of containers.

Kubernetes is also referred to as k8s, as there are 8 characters between k and s.

Kubernetes is highly inspired by the Google Borg system, a container orchestrator for its global operations for more than a decade. It is an open source project written in the Go language and licensed under the Apache License, Version 2.0.

Kubernetes was started by Google and, with its v1.0 release in July 2015, Google donated it to the Cloud Native Computing Foundation (CNCF). We will talk more about CNCF later in this chapter.

## Kubernetes Features
- Automatic bin packing
- Self-healing
- Horizontal scaling
- Service discovery and Load balancing
- Automated rollouts and rollbacks
- Secret and configuration management
- Storage orchestration
- Batch execution

## Kubernetes Architecture
- One or more **master nodes**
- One or more **worker nodes**
- Distributed key-value store, such as **etcd**

![alt text](/Kubernetes_Architecture1.png)

## Master Node
The **master node** provides a running environment for the control plane responsible for managing the state of a Kubernetes cluster, and it is the brain behind all operations inside the cluster. 

A master node has the following components:
- API server
- Scheduler
- Controller managers
- [etcd](https://github.com/etcd-io)

### API Server
All the administrative tasks are coordinated by the **kube-apiserver**, a central **control plane** component running on the master node.

### Scheduler
The role of the **kube-scheduler** is to assign new objects, such as pods, to nodes.

### Controller Managers
The **controller managers** are control plane components on the master node running controllers to regulate the state of the Kubernetes cluster.

The **kube-controller-manager** runs controllers responsible to act when nodes become unavailable, to ensure pod counts are as expected, to create endpoints, service accounts, and API access tokens.

The **cloud-controller-manager** runs controllers responsible to interact with the underlying infrastructure of a cloud provider when nodes become unavailable, to mange storage volumes when provided by a cloud service, and to manage load balancing and routing.

### etcd
[etcd](https://github.com/etcd-io) is a distributed key-value data store used to persist a Kubernetes cluster
's state. etcd is written in the **Go** programming language. In Kubernetes, besides storing the cluster state, etcd is also used to store configuration details such as subnets, ConfigMaps, Secrets, etc.

## Worker Node
A **worker node** provides a running environment for client applications.

### Container runtime
- [Docker](https://www.docker.com/) - although a container platform which uses **containerd** as a container runtime, it is the most widely used container runtime with Kubernetes
- [CRI-O](https://cri-o.io/) - a lightweight container runtime for Kubernetes, it also supports Docker image registries
- [containerd](https://containerd.io/) - a simple and portable contianer runtime providing robustness


### kubelet
The **kubelet** is an agent running on each node and communicates with the control plane components from the master node. 

The kubelet connects to the container runtime using **Container Runtime Interface (CRI)**. CRI consists of protocol buffers, gRPC API, and libraries.

![alt text](/CRI.png)

As shown above, the kubelet acting as **grpc** client connects to the **CRI shim** acting as **grpc server** to perform container and image operations. CRI implements two servcies: **ImageService** and **RuntimeService**. The **ImageService** is responsible for all the image-related operations, while the **RuntimeService** is responsible for all the Pod and container-related operations.

### kubelet - CRI shims

### kube-proxy

### Addons for DNS, Dashboard, cluster-level monitoring and logging

## Ingress
- [ ] https://kubernetes.io/docs/concepts/services-networking/ingress/ 
- [ ] [LinuxFoundationX: LFS158x - Introduction to Kubernetes](https://courses.edx.org/courses/course-v1:LinuxFoundationX+LFS158x+2T2019/course/)