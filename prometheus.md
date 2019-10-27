# Prometheus
Deploy Prometheus
```bash
$ kubectl create namespace prometheus
helm install stable/prometheus \
    --name prometheus \
    --namespace prometheus \
    --set alertmanager.persistentVolume.storageClass="gp2" \
    --set server.persistentVolume.storageClass="gp2"
```

Check if Prometheus components deployed as expected
```
$ kubectl get all -n prometheus
```
In order to access the Prometheus server URL, we are going to use the [kubectl port-forward](https://kubernetes.io/docs/tasks/access-application-cluster/port-forward-access-application-cluster/) command to access the application.
```bash
$ kubectl port-forward -n prometheus deploy/prometheus-server 8080:9090
```