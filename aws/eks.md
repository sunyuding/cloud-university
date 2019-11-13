# Amazon Elastic Kubernetes Service (EKS)
- [Amazon EKS Workshop](https://eksworkshop.com)
- [Amazon Elastic Container Service for Kubernetes (EKS) Primer](https://www.aws.training/Details/eLearning?id=32894)
- Contianer management platform
    - Amazon Elastic Container Service (ECS)
    - Docker Swarm
    - [kubernetes](/kubernetes.md)
- Cluster Autoscaler for AWS provides integration with Auto Scaling groups.
- AWS manage the **control plane**
- You take care of provisioning, updating, scaling, patching the **data plane**
- master
    - Controller manager
    - Cloud controler
    - Scheduler
- worker
- ReplicaSets
- kubectl
- Dashboard

What is the basic unit of deployment in Kubernetes?
- Pods

What is a Kubernetes service?
- A logical collection of pods and a means to access them

![](codepipeline.png)

What form of Kubernetes does EKS support?
- Native, upstream Kubernetes

Which components are managed by EKS?
- The Kubernetes control plane (master)

Customers are responsible for managing the EKS work nodes.

What is the recommended method to update EKS worker nodes to a new version of Kubernetes?
- Replace the nodes with the new AMI and migrate your pods to the new group.

What type of service can be accessed from outside the cluster?
- NodePort
- LoadBalancer

![](auth.png)

![](sso.png)

#### Secrets

How are secrets in **Secrets Manager** usually accessed?
- Through **System Manager Parameter Store**

#### eksctl
eksctl is an open source tool for managing EKS clusters developed by Weaveworks and AWS

[LAUNCH USING EKSCTL](https://eksworkshop.com/eksctl/)

```
eksctl is a tool jointly developed by AWS and Weaveworks that automates much of the experience of creating EKS clusters.
```

```
$ eksctl create cluster -f example.yaml
```

- Autoscaling node groups
    - Define a maximum and minimum number of nodes and scale based on cluster load.

https://github.com/fluxcd/multi-tenancy

https://eksctl.io/

#### upgrade
You are responsible for updating the EKS **worker node**.

There are 2 ways
1. Node group
2. CloudFormation

What is the recommended method to update EKS worker nodes to a new version of Kubernetes?
- Replace the nodes with the new AMI and migrate your pods to the new group.

### [Updating an Amazon EKS Cluster Kubernetes Version](https://docs.aws.amazon.com/eks/latest/userguide/update-cluster.html)