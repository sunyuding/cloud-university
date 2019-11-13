# Ingress
- [ ] https://kubernetes.io/docs/concepts/services-networking/ingress/ 
- [ ] [LinuxFoundationX: LFS158x - Introduction to Kubernetes]
(https://courses.edx.org/courses/course-v1:LinuxFoundationX+LFS158x+2T2019/course/)

According to [kubernetes.io](https://kubernetes.io/docs/concepts/services-networking/ingress/),
```
"An Ingress is a collection of rules that allow inbound connections to reach the cluster Services."
```
![Image of Ingress](ingress_updated.png)

![Image of Ingress URL Mapping](ingress_URL_mapping.png)

## Ingress Controller
An [Ingress Controller](https://kubernetes.io/docs/concepts/services-networking/ingress-controllers/) is an application watching the Master Node's API server for changes in the **Ingress** resources and updates the Layer 7 Load Balancer accordingly. 

Start the Ingress Controller with Minikube
```bash
$ minikube addons enable ingress
```

## Deploy an Ingress Resource
```bash
$ kubectl create -f virtual-host-ingress.yaml
```

## Access Services Using Ingress