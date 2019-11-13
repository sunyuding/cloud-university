# Kubernetes

## Kubernetes Journey
- [Introduction to Kubernetes]() by the linux foundation on EDX (free).
- Participating in activities and discussions organized by the Kubernetes community
- Attending events organized by the **Cloud Native Computing Foundation** and **The Linux Foundation**
- Expanding your Kubernetes knowledge and skills by enrolling in the self-paced [LFS258 - Kubernetes Fundamentals](https://training.linuxfoundation.org/training/kubernetes-fundamentals/),  [LFD259 - Kubernetes for - Developers](https://training.linuxfoundation.org/training/kubernetes-for-developers/), or the instructor-led [LFS458 - Kubernetes Administration](https://training.linuxfoundation.org/training/kubernetes-administration/) and [LFD459 - Kubernetes for App Developers](https://training.linuxfoundation.org/training/kubernetes-for-app-developers/), paid courses offered by The Linux Foundation 
- Preparing for the [Certified Kubernetes Administrator](https://www.cncf.io/certification/cka/) or the [Certified Kubernetes Application Developer](https://www.cncf.io/certification/ckad/) exams, offered by the Cloud Native Computing Foundation
  - [Certified Kubernetes Administrator AND Certified Kubernetes Application Developer Candidate Handbook](https://training.linuxfoundation.org/wp-content/uploads/2019/08/CKA-CKAD-Candidate-Handbook-8.5.19.pdf)
  - [My Feedback about CKA and CKAD](https://medium.com/@ikaboubi/my-feedback-about-cka-and-ckad-e82a35585fe9)
    - [Scalable Microservices with Kubernetes
by Google (free)](https://www.udacity.com/course/scalable-microservices-with-kubernetes--ud615).
    - Kubernetes Fundamentals (paid).
    - [Kuberntes The Hard Way by Kelsey Hightower(free)](https://github.com/kelseyhightower/kubernetes-the-hard-way)
    - Documentation kubernetes.io (free).
  - [https://talkcloudlytome.com/thoughts-on-the-kubernetes-cka-and-ckad-certifications/](https://talkcloudlytome.com/thoughts-on-the-kubernetes-cka-and-ckad-certifications/)
    - ["Kubernetes In Action" by Marko Lukša](https://www.manning.com/books/kubernetes-in-action)
  - [How I passed the CKA (Certified Kubernetes Administrator) Exam](https://medium.com/platformer-blog/how-i-passed-the-cka-certified-kubernetes-administrator-exam-8943aa24d71d)
    - https://linuxacademy.com/course/cloud-native-certified-kubernetes-administrator-cka/
    - https://github.com/dgkanatsios/CKAD-exercises?source=post_page-----8943aa24d71d----------------------
    - https://github.com/walidshaari/Kubernetes-Certified-Administrator?source=post_page-----8943aa24d71d----------------------
    - Community discussion page is also accessible to you since it comes under the kubernetes.io domain, which is a great place to search for some problems you may get. https://discuss.kubernetes.io
    - If you are unsure of the spec or parameters of a yaml, always use `kubectl explain <resource>.<key>` which is a great way to get a quick look at the keys available to you.
  - https://github.com/walidshaari/Kubernetes-Certified-Administrator
  - [Amazon EKS Workshop](https://eksworkshop.com)

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
    If you do not already have a hypervisor installed, install one of these now:
    - HyperKit
    - VirtualBox
    - VMware Fusion

[Minikube installation](https://kubernetes.io/docs/tasks/tools/install-minikube/)

Read more: [How to Install Kubernetes on Mac](https://matthewpalmer.net/kubernetes-app-developer/articles/guide-install-kubernetes-mac.html)

```bash
➜  ~ minikube start
😄  minikube v1.3.1 on Darwin 10.14.6
🔥  Creating virtualbox VM (CPUs=2, Memory=2000MB, Disk=20000MB) ...
🐳  Preparing Kubernetes v1.15.2 on Docker 18.09.8 ...
💾  Downloading kubeadm v1.15.2
💾  Downloading kubelet v1.15.2
🚜  Pulling images ...
🚀  Launching Kubernetes ...
⌛  Waiting for: apiserver proxy etcd scheduler controller dns
🏄  Done! kubectl is now configured to use "minikube"
```

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

```
$ kubectl get namespaces

NAME          STATUS    AGE
default       Active    1d
kube-system   Active    1d
kube-public   Active    1d
```

Kubernetes starts with three **initial namespaces**:
- **default** The default namespace for objects with no other namespace
- **kube-system** The namespace for objects created by the Kubernetes system
- **kube-public** This namespace is created automatically and is readable by all users (including those not authenticated). 

## Kubernetes Building Blocks

### Deployment Rolling Update and Rollback
```
$ kubectl create deployment mynginx --image=nginx:1.15-alpine

deployment.apps/mynginx created
```

Get the deployment, replicaset and pod with lable mynginx.
```
$ kubectl get deploy,rs,po -l app=mynginx
```

Scale the deployment up to 3 replicas.
```
$ kubectl scale deploy mynginx --replicas=3

deployment.extensions/mynginx scaled
```

```
$ kubectl describe deploy mynginx
```

For the purpose of rolling updates and rollbacks, we could use the `kubectl rollout` command.


Check the rollout history
```
$ kubectl rollout history deploy mynginx
```

```
$ kubectl rollout history deploy mynginx --revision=1 
```

A rolling update does not necessarily mean an upgrade. I could perform a rolling update and actually move down in the image version.
```
$ kubectl set image deployment mynginx nginx=nginx:1.16-alpine

deployment.extensions/mynginx image updated
```

Rollback to the previous revision.
```
$ kubectl rollout undo deployment mynginx --to-revision=1

deployment.extensions/mynginx rolled back
```

## Authentication, Authorization, Admission Control
- Authentication
- Authorization
- Admission Control

![Image of Accessing the API](access-k8s.png)

### Authentication
Kubernetes does not have an object called *user*, not does it store *usernames* or other related details in its object store. However, even without that, Kubernetes can use usernames for access control and request logging.

Kubernetes has two kinds of users:
- Normal Users

    They are managed outside of the Kubernetes cluster via independent services like User/Client Certificates, a file listing usernames/passwords, Google accounts, etc.

- Service Accounts
    With **Service Account** users, in-cluster processes communicate with the API server to perform different operations. Most of the **Service Account** users are created automatically via the API server, but they can also be created manually. The **Service Account** users are tied to a given Namespace and mount the respective credentials to communicate with the API server as **Secrets**.

If properly configured, Kubernetes can also support **anonymous requests**, along with requests from **Normal Users** and **Service Accounts**. **User impersonation** is also supported for a user to be able to act as another user, a useful feature for administrators when troubleshooting authorization policies.

For authentication, Kubernetes uses different [authentication modules](https://kubernetes.io/docs/reference/access-authn-authz/authentication/#authentication-strategies):
- Client Certificates

    client-ca-file=SOMEFILE

- Static Token File

    --token-auth-file=SOMEFILE

- Bootstrap Tokens

- Static Password File

    --basic-auth-file=SOMEFILE

- Service Account Tokens

- OpenID Connect Tokens

- Webhook Token Authentication

- Authenticating Proxy

We can enable multiple authenticators, and the first module to successfully authenticate the request **short-circuits** the evaluation. In order to be successful, you should enable at least two methods: the **service account tokens** authenticator and one of the user authenticators. 

### Authorization
Authorization modules:
- Node Authorizer
- Attribute-Based Access Control (ABAC) Authorizer
- Webhook Authorizer
- Role-Based Access Control (RBAC) Authorizer
    - Role
    - ClusterRole

### Admission Control

---

## Services
**Services**, used to group Pods to provide common access points from the external world to the containerized applications. 

### Connecting Users to Pods
Kubernetes provides a higher-level abstraction called [Service](), which logically groups Pods and defines a policy to access them. This grouping is achieved via **Labels** and **Selectors**.

### Services
In teh following graphicall representation, **app** is the Label key, **frontend** and **db** are Label values for different Pods. 

Using the selectors **app==frontend** and **app==db**, we group Pods into two logical sets: one with 3 Pods, and one with a single Pod.

We assign a name to the logical grouping, referred to as a **Service**. In our example, we create two Services, **frontend-svc**, and **db-svc**.

![Image of Grouping of Pods using Labels and Selectors](services2.png)

### Service Object Example
```
kind: Service
apiVersion: v1
metadata:
  name: frontend-svc
spec:
  selector:
    app: frontend
  ports:
  - protocol: TCP
    port: 80
    targetPort: 5000
```

### kube-proxy
All worker nodes run a daemon called [kube-proxy](https://kubernetes.io/docs/concepts/services-networking/service/#virtual-ips-and-service-proxies), which watches the API server on the master node for the addition and removal of Services and endpoints. 

![Image of kube-proxy, Services, and Endpoints](kubeproxy.png)

### Service Discovery
- Environment Variables
- DNS

### ServiceType: ClusterIP and NodePort

### ServiceType: LoadBalancer

### ServiceType: ExternalIP

### ServiceType: ExternalName

## Deploying a Stand-Alone Application

### Liveness
**Liveness Probe** checks on an application's health, and if the health check fails, **kubelet** restats the affected container automatically.

**Liveness Probes** can be set by defining:
- Liveness command
- Liveness HTTP request
- TCP Liveness Probe

### Liveness command
The existence of the **/tmp/healthy** file is configured to be checked every 5 seconds using the **periodSeconds** parameter. 

### Liveness HTTP Request
```
livenessProbe:
      httpGet:
        path: /healthz
        port: 8080
        httpHeaders:
        - name: X-Custom-Header
          value: Awesome
      initialDelaySeconds: 3
      periodSeconds: 3
```

### TCP Liveness Probe
```
livenessProbe:
      tcpSocket:
        port: 8080
      initialDelaySeconds: 15
      periodSeconds: 20
```

### Readiness Probes
```
readinessProbe:
  exec:
    command:
    - cat
    - /tmp/healthy
  initialDelaySeconds: 5
  periodSeconds: 5
```

## Kubernetes Volume Management
Kubernetes uses **Volumes** of several types and a few other forms of storage resources for container data management. 

### Volumes
As we know, containers running in Pods are ephemeral in nature. All data stored inside a container is deleted if the container crashes. However, the **kubelet** will restart it with a clean slate, which means that it will not have any of the old data.

To overcome this problem, Kubernetes uses [Volumes](https://kubernetes.io/docs/concepts/storage/volumes/). A Volume is essentially a directory backed by a storage medium. The storage medium, content and access mode are determined by the Volume Type.

 ![](podvolume.png)

## RBAC
Basically, the RBAC model is based on three components: 
- Roles
- ClusterRoles 
  - The “edit” role lets users perform basic actions like deploying pods.
  - The “view” lets users review specific resources that are non-sensitive.
  - The “admin” role lets a user manage a namespace.
  - The “cluster-admin” allows access to administer a cluster.
- Subjects

## ConfigMaps and Secrets
While deploying an application, we may need to pass such runtime parameters like configuration details, permissions, passwords, tokens, etc. Let's assume we need to deploy ten different applications for our customers, and for each customer, we need to display the name of the company in the UI. Then, instead of creating ten different Docker images for each customer, we may just use the template image and pass customers' names as runtime parameters. In such cases, we can use the **ConfigMap API** resource. Similarly, when we want to pass sensitive information, we can use the **Secret API** resource.

### ConfigMaps
- [ConfigMaps](https://kubernetes.io/docs/tasks/configure-pod-container/configure-pod-configmap/) allow us to decouple the configuration details from the container image. 
- [ConfigMap | Kubernetes Engine Documentation | Google Cloud](https://cloud.google.com/kubernetes-engine/docs/concepts/configmap)
- [Ultimate Guide to ConfigMaps in Kubernetes](https://matthewpalmer.net/kubernetes-app-developer/articles/ultimate-configmap-guide-kubernetes.html)

### Secrets
It is important to keep in mind that the **Secret** data is stored as plain text inside **etcd**, therefore administrators must limit access to the API server and **etcd**.

```bash
$ kubectl describe secret my-password
```
They do not reveal the content of the Secret. The type is listed as **Opaque**.

### Use Secrets Inside Pods
- Using Secrets as Environment Variables
- Using Secrets as Files from a Pod

## [Ingress](ingress.md)

## Annotations
With [Annotations](https://kubernetes.io/docs/concepts/overview/working-with-objects/annotations/), we can attach arbitrary non-identifying metadata to any objects, in a key-value format:
```
"annotations": {
  "key1" : "value1",
  "key2" : "value2"
}
```

Unlike Labels, annotations are not used to identify and select objects. Annotations can be used to:
- Store build/release IDs, PR numbers, git branch, etc.
- Phone/pager numbers of people responsible, or directory entries specifying where such information can be found
- Pointers to logging, monitoring, analytics, audit repositories, debugging tools, etc.

```bash
$ kubectl describe deployment webserver
```

## Jobs and CronJobs
A [Job](https://kubernetes.io/docs/concepts/workloads/controllers/jobs-run-to-completion/) creates one or more Pods to perform a given task.

## Quota Management
- Compute Resource Quota
- Storage Resource Quota
- Object Count Quota

## Autoscaling

## Service


## [Controllers](https://kubernetes.io/docs/concepts/workloads/controllers)
### StatefulSets
[StatefulSet Basics - Kubernetes](https://kubernetes.io/docs/tutorials/stateful-application/basic-stateful-set/)

### DaemonSets

## Kubernetes Federation

## Custom Resources

## [Helm](helm.md) 

## Configuration

### [The KUBECONFIG environment variable](https://kubernetes.io/docs/concepts/configuration/organize-cluster-access-kubeconfig/#the-kubeconfig-environment-variable)
The KUBECONFIG environment variable holds a list of kubeconfig files. If the `KUBECONFIG` environment variable doesn’t exist, `kubectl` uses the default kubeconfig file, `$HOME/.kube/config`.

### kubectl Configuration File
To look at the connection details, we can either see the content of the `~/.kube/config` file (on Linux) or run the following command:
```bash
$ kubectl config view
```

## Kustomize
Kubernetes native configuration management

## Sealed Secrets
https://github.com/bitnami-labs/sealed-secrets
```
$ brew install kubeseal
```

## Flux
```
$ brew install fluxctl
```

## Kubernetes Community
With more than [53K GitHub stars](https://github.com/kubernetes/kubernetes/), Kubernetes is one of the most popular open source projects. The community members not only help with the source code, but they also help with sharing the knowledge. The community engages in both online and offline activities.

Currently, there is a project called [K8s Port](https://github.com/kubernetes/kubernetes/), which recognizes and rewards community members for their contributions to Kubernetes. This contribution can be in the form of code, attending and speaking at meetups, answering questions on Stack Overflow, etc.

**Weekly Meetings**

A weekly community meeting happens using video conference tools. You can request a calendar invite from [here](https://groups.google.com/forum/#!forum/kubernetes-community-video-chat).

**Meetup Groups**

There are many [meetup groups](https://www.meetup.com/topics/kubernetes/) around the world, where local community members meet at regular intervals to discuss Kubernetes and its ecosystem.

**Slack Channels**

Community members are very active on the [Kubernetes Slack](https://kubernetes.slack.com/). 

**Mailing Lists**
There are Kubernetes [users](https://groups.google.com/forum/#!forum/kubernetes-users) and [developer](https://groups.google.com/forum/#!forum/kubernetes-users) mailing lists, which can be joined by anybody interested.

## kubectl CLI
- [Kubernetes commands reference](https://kubernetes.io/docs/reference/generated/kubectl/kubectl-commands)
- Kubectl cheatsheet that would help you right out with most questions in your exams. https://kubernetes.io/docs/reference/kubectl/cheatsheet
- (Tutorial) Kubernetes Bootcamp - https://kubernetesbootcamp.github.io/kubernetes-bootcamp/index.html
- (Course) Scalable Microservices with Kubernetes - https://br.udacity.com/course/scalable-microservices-with-kubernetes--ud615/
- https://kubernetes.io/docs/tutorials/kubernetes-basics/
- Command reference: https://kubernetes.io/docs/reference/generated/kubectl/kubectl-commands

---

## Amazon EKS

### Configure Liveness, Readiness and Startup Probes
#### Liveness Probe
The kubelet uses **liveness probes** to know when to restart a Container.

#### Readiness Probe
The kubelet uses **readiness probes** to know when a Container is ready to start accepting traffic.

#### Startup Probe
The kubelet uses **startup probes** to know when a Container application has started.

---

## Troubleshooting
### [Error: incompatible versions client[v2.14.3] server[v2.12.3]](https://github.com/helm/charts/issues/5239)

`helm init --upgrade` upgraded the server version

### [forbidden: User "system:serviceaccount:kube-system:default" cannot get namespaces in the namespace "default](https://github.com/fnproject/fn-helm/issues/21)

```
$ kubectl create serviceaccount --namespace kube-system tiller
$ kubectl create clusterrolebinding tiller-cluster-rule --clusterrole=cluster-admin --serviceaccount=kube-system:tiller
$ kubectl patch deploy --namespace kube-system tiller-deploy -p '{"spec":{"template":{"spec":{"serviceAccount":"tiller"}}}}'
```

### CrashLoopBackOff
**CrashLoopBackOff** indicates that a container is repeatedly crashing after restarting. A container might crash for many reasons, and checking a Pod's logs might aid in troubleshooting the root cause.

```
kubectl get sts

kubectl describe sts concourse-postgresql

helm install stable/concourse --dry-run --debug
```

### [Storage Classes](https://kubernetes.io/docs/concepts/storage/storage-classes/)

```
kubectl get storageClass

kubectl edit storageClass gp2
```

[Amazon EBS Volume Types](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/EBSVolumeTypes.html): The default volume type is **General Purpose SSD (gp2)**.