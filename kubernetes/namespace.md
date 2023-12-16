#Namespaces

In a Kubernetes cluster, namespaces provide a way to partition resources and isolate workloads. They act as virtual clusters within a physical cluster, enabling multiple teams or projects to run independently. Switching namespaces allows administrators or developers to work with different sets of resources within the same cluster.

###List the available namespaces

```
$ kubectl get namespaces
```

```
$ kubectl get namespaces --show-labels
```

###Create new namespaces

Use the file `namespace-dev.yaml` which describes a development namespace:

```
apiVersion: v1
kind: Namespace
metadata:
  name: development
  labels:
    name: development
```

###Switch namespace
```
$ kubectl config set-context --current --namespace=<namespace-name>
```

###Using the kubectl Command With the –namespace Flag

```
$ kubectl get pods --namespace=default
```

###Setting Namespace in Kubernetes Configuration Files

To set the default namespace, we need to open our Kubernetes configuration file (usually located at ~/.kube/config) and locate the contexts section. We can add or modify the context entry to include the namespace field:

```
contexts:
- context:
    cluster: my-cluster
    user: my-user
    namespace: my-namespace
  name: my-context
```