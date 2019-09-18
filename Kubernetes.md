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
The **kube-proxy** is the network agent which runs on each node responsible for dynamic updates and maintenance of all networking ruls on the node.

### Addons

### Nerworking Challenges
- Container-to-container communication inside Pods
- Pod-to-Pod communication on the same node and across cluster nodes
- Pod-to_Service communication within the same namespace and across cluster namespaces
- External-to-Service communication for clients to access applications in a cluster

### Container-to-Container Communication Inside Pods
Making use of the underlying host operating system's kernel features, a container runtime creates an isolated network space for each container it starts. On Linux, that isolated network space is referred to as a **network namespace**. A network namespace is shared across containers, or with the host operating system. When a Pod is started, a network namespace is created inside the Pod, and all containers running inside the Pod will share the network namespace so that they can talk to each other via localhost.

### Pod-to-Pod Communication Across Nodes
This model is called "**IP-per-Pod" and ensures Pod-to-Pod communication, just as VMs are able to communicate with each other.

![alt text](/Container_Network_Interface_CNI.png)

### Pod-to-External World Communication
By exposing services to the external world with **kube-proxy**, applications become accesible from outside the cluster over a virtual IP.

## Installing Kubernetes
### Kubernetes Configuration
Kubernetes can be installed using different configurations. The four major installation types are briefly presented below:
- All-in-One Single-Node Installation
- Single-Node etcd, Single-Master and Multi-Worker Installation
- Single-Node etcd, Multi-Master and Multi-Worker Installation
- Multi-Node etcd, Multi-Master and Multi-Worker Installation

### Infrastructure for Kubernetes Installation
[Minikube](https://kubernetes.io/docs/getting-started-guides/minikube/) is the preferred and recommended way to create an all-in-one kubernetes setup locally.

### On-Premise Installation
- On-Premise VMs
- On-Premise Bare Metal

### Cloud Installation
- Hosted Solutions
    - Google Kubernetes Engine (GKE)
    - Amazon Elastic Container Service for Kubernetes (EKS)
- Turnkey Cloud Solutions
- Turnkey On-Premise Solutions

### Kubernetes Installation Tools/Resources
- kubeadm
- kubespray
- kops
- kube-aws

## Minikube - A Local Single-Node Kubernetes Cluster
[Minikube](https://kubernetes.io/docs/setup/minikube/) is the easiest and most recommended way to run an all-in-one Kubernetes cluster locally on our workstations.

- kubectl 
- Type-2 Hypervisor

[Minikube installation](https://kubernetes.io/docs/tasks/tools/install-minikube/)

## Accessing Minikube
Any healthy running Kubernetes cluster can be accessed via any one of the following methods:
- Command Line Interface (CLI) tools and scripts
- Web-based User Interface (Web UI) from a web browser
- APIs from CLI or programmatically

### Command Line Interface (CLI)
[kubectl](https://kubernetes.io/docs/reference/kubectl/overview/) is the **Kubernetes Command Line Interface (CLI) client** to manage cluster resources and applications. 

### Web-based User Interface (Web UI)
The [Kubernetes Dashboard](https://kubernetes.io/docs/tasks/access-application-cluster/web-ui-dashboard/) provides a **Web-based User Interface (Web UI)** to interact with a Kubernetes cluster to manage resources and containerized applications. 

### Accessing Minikube: APIs
As we know, Kubernetes has the **API server**, and operators/users connect to it from the external world to interact with the cluster. 

![Image of HTTP API Space of Kubernetes](api-server-space_.jpg)

HTTP API space of Kubernetes can be divided into three independent groups:
- Core Group (/api/v1)
- Named Group
- System-wide

### kubectl
There are different methods that can be used to install kubectl, which are mentioned in the [Kubernetes documentation](https://kubernetes.io/docs/tasks/tools/install-kubectl/).

### kubectl Configuration File
Too look at the connection details, we can either see the content of the `~/.kube/config` file (on Linux) or run the following command:
```bash
$ kubectl config view
```

Once kubectl is installed, we can get information about the Minikube cluster with the command:
```bash
$ kubectl cluster-info
```

### Kubernetes Dashboard
As mentioned earlier, the [Kubernetes Dashboard](https://kubernetes.io/docs/tasks/access-application-cluster/web-ui-dashboard/) provides a web-based user interface for Kubernetes cluster management. To access the dashboard from Minikube, we can use the minikube dashboard command, which opens a new tab on our web browser, displaying the Kubernetes Dashboard:
```bash
$ minikube dashboard
```

### The 'kubectl proxy' Command
```bash
$ kubectl proxy
```

### APIs - with 'kubectl proxy'
When kubectl proxy is running, we can send requests to the API over the localhost on the proxy port 8001 (from another terminal, since the proxy locks the first terminal):
```bash
$ curl http://localhost:8001/
```

### APIs - without 'kubectl proxy'
When not using the **kubectl proxy**, we need to authenticate to the API server when sending API requests. We can authenticate by providing a **Bearer Token** when issuing a `curl`, or by providing a set of **keys** and **certificates**. 

## Kubernetes Building Blocks

### Pods

### Labels
[Labels]() are key-value pairs attached to Kubernetes objects(e.g. Pods, ReplicaSets)

### Label Selectors
Controllers use [Label Selector](https://kubernetes.io/docs/concepts/overview/working-with-objects/labels/#label-selectors) to select a subset of objects. Kubernetes supports two types of Selectors:
- Equality-Based Selectors
- Set-Based Selectors

### Namespace
If 
https://kubernetes.io/docs/concepts/overview/working-with-objects/namespaces/

### Addons for DNS, Dashboard, cluster-level monitoring and logging


## Helm 
https://helm.sh/

## Ingress
- [ ] https://kubernetes.io/docs/concepts/services-networking/ingress/ 
- [ ] [LinuxFoundationX: LFS158x - Introduction to Kubernetes](https://courses.edx.org/courses/course-v1:LinuxFoundationX+LFS158x+2T2019/course/)


## Commands
Command to delete all pods in a single kubernetes namespace. 
```bash
kubectl delete --all pods --namespace=<foo>
```






