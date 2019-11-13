# Concourse-CI
- [Doc](https://concourse-ci.org/docs.html)

- [Control Tower: deploy and operate Concourse-ci in a single command](https://github.com/EngineerBetter/control-tower)

- [Control Tower for Concourse (Beta)](https://docs.pivotal.io/partners/engineerbetter-control-tower/index.html)

- Concourse tutorials: [Concourse Tutorial by Stark & Wayne](https://concoursetutorial.com)

```
$ fly --target <hello-world> login --insecure --concourse-url <https://52.11.124.221> --username <admin> --password <5pqvo9482npglqjc0lhw>
```

When we use the fly command we will target this Concourse API using `fly --target tutorial`.


- [What is concourse and getting started](https://starkandwayne.com/blog/video-001-what-is-concourse-and-getting-started/)

We can first start moving webapps and other random jobs over to Concourse.  However we'll need to think/plan how we want to control jobs and common pieces.

## Kubernetes

[Install concourse in a k8s cluster.](https://github.com/helm/charts/tree/master/stable/concourse)

Building a continious deployment pipeline with Kubernetes and Concourse-CI: https://blog.alterway.fr/en/building-a-continious-deployment-pipeline-with-kubernetes-and-concourse-ci.html

[Concourse Pipeline (Kubernetes)](https://cloud.spring.io/spring-cloud-pipelines/multi/multi_concourse-pipeline-k8s.html)


[Installing Concourse 5.0 on Kubernetes using Helm](https://medium.com/concourse-ci/installing-concourse-5-0-on-pivotal-container-service-using-helm-9f20e4e1b8bf)

```
➜  ~ helm del --purge concourse
release "concourse" deleted

➜  ~ helm install stable/concourse --name concourse
Error: release concourse failed: namespaces "concourse-main" already exists

➜  ~ helm ls --all
NAME     	REVISION	UPDATED                 	STATUS	CHART          	APP VERSION	NAMESPACE
concourse	1       	Wed Nov  6 17:10:06 2019	FAILED	concourse-8.2.5	5.5.0      	default
```


```
➜  ~ helm status concourse
LAST DEPLOYED: Thu Nov  7 15:59:16 2019
NAMESPACE: default
STATUS: DEPLOYED

RESOURCES:
==> v1/ConfigMap
NAME              DATA  AGE
concourse-worker  1     21m

==> v1/Namespace
NAME            STATUS  AGE
concourse-main  Active  21m

==> v1/Pod(related)
NAME                            READY  STATUS   RESTARTS  AGE
concourse-postgresql-0          1/1    Running  0         21m
concourse-web-699fc698b5-jdsbg  1/1    Running  0         21m
concourse-worker-0              1/1    Running  0         21m
concourse-worker-1              1/1    Running  0         21m

==> v1/Secret
NAME                  TYPE    DATA  AGE
concourse-postgresql  Opaque  1     21m
concourse-web         Opaque  4     21m
concourse-worker      Opaque  2     21m

==> v1/Service
NAME                           TYPE       CLUSTER-IP     EXTERNAL-IP  PORT(S)            AGE
concourse-postgresql           ClusterIP  172.20.171.61  <none>       5432/TCP           21m
concourse-postgresql-headless  ClusterIP  None           <none>       5432/TCP           21m
concourse-web                  ClusterIP  172.20.11.129  <none>       8080/TCP,2222/TCP  21m
concourse-worker               ClusterIP  None           <none>       <none>             21m

==> v1/ServiceAccount
NAME              SECRETS  AGE
concourse-web     1        21m
concourse-worker  1        21m

==> v1beta1/ClusterRole
NAME           AGE
concourse-web  21m

==> v1beta1/Deployment
NAME           READY  UP-TO-DATE  AVAILABLE  AGE
concourse-web  1/1    1           1          21m

==> v1beta1/PodDisruptionBudget
NAME              MIN AVAILABLE  MAX UNAVAILABLE  ALLOWED DISRUPTIONS  AGE
concourse-worker  1              N/A              1                    21m

==> v1beta1/Role
NAME              AGE
concourse-worker  21m

==> v1beta1/RoleBinding
NAME                AGE
concourse-web-main  21m
concourse-worker    21m

==> v1beta1/StatefulSet
NAME              READY  AGE
concourse-worker  2/2    21m

==> v1beta2/StatefulSet
NAME                  READY  AGE
concourse-postgresql  1/1    21m


NOTES:

* Concourse can be accessed:

  * Within your cluster, at the following DNS name at port 8080:

    concourse-web.default.svc.cluster.local

  * From outside the cluster, run these commands in the same shell:

    export POD_NAME=$(kubectl get pods --namespace default -l "app=concourse-web" -o jsonpath="{.items[0].metadata.name}")
    echo "Visit http://127.0.0.1:8080 to use Concourse"
    kubectl port-forward --namespace default $POD_NAME 8080:8080
* If this is your first time using Concourse, follow the tutorials at https://concourse-ci.org/tutorials.html

*******************
******WARNING******
*******************

You are using the "naive" baggage claim driver, which is also the default value for this chart.

This is the default for compatibility reasons, but is very space inefficient, and should be changed to either "btrfs" (recommended) or "overlay" depending on that filesystem's support in the Linux kernel your cluster is using.

Please see https://github.com/concourse/concourse/issues/1230 and https://github.com/concourse/concourse/issues/1966 for background.

*******************
******WARNING******
*******************

You're using the default "test" user with the default "test" password.

Make sure you either disable local auth or change the combination to something more secure, preferably specifying a password in the bcrypted form.

Please see `README.md` for examples.
```

## Auth
### Login
(https://medium.com/concourse-ci/oh-auth-f4fe68438171)
- external auth providers

- local Concourse user

## Troubleshooting
```
helm install stable/concourse --dry-run --debug
```

