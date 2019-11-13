# Helm

To deploy an application, we use different Kubernetes manifests, such as **Deployments**, **Services**, Volume Claims, **Ingress**, etc. Sometimes, it can be tiresome to deploy them one by one. We can bundle all those manifests after templatizing them into a well-defined format, along with other metadata. Such a bundle is referred to as **Chart**. These **Charts** can then be served via repositories, such as those that we have for **rpm** and **deb** packages.

[Helm](https://helm.sh/) is a **package manager** (analogous to **yum** and **apt** for Linux) for Kubernetes that packages multiple Kubernetes resources into a single logical deployment unit called **Chart**.

The client **helm** connects to the server **tiller** to manage **Charts**. Charts submitted for Kubernetes are available [here](https://github.com/helm/charts).

[Helm commands](https://helm.sh/docs/helm/)

Remove the release from the store and make its name free for later use
```
$ helm delete --purge concourse
```


```
$ helm install stable/concourse --name concourse
```


```
$ helm ls --all
```