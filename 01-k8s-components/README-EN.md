# Basic Components

[EN](./README-EN.md)/[TH](./README.md)

[This](https://www.trendmicro.com/vinfo/us/security/news/security-technology/the-basics-of-keeping-your-kubernetes-cluster-secure-part-1) image represent simple K8S Cluster
![](https://documents.trendmicro.com/images/TEx/articles/diagram-of-a-Kubernetes-cluster-and-its-components.jpg) 

To retrieve all the nodes in our cluster, use this command.

```bash
kubectl get nodes
```

The output 
```
NAME      STATUS   ROLES                  AGE    VERSION
ichiban   Ready    control-plane,master   2d6h   v1.25.4+k3s1
niban     Ready    <none>                 2d6h   v1.25.4+k3s1
```

- `NAME` : name of each node
- `STATUS` : each node's status. There are Ready, NotReady or SchedulingDisabled, etc. For more information, see the [official document](https://kubernetes.io/docs/concepts/overview/).
- `ROLES` : each node's role. The `control-plane,master` takes care of scheduling the cluster, and a `<none>` just a worker node.
- `AGE` : how long the node has been deployed (not the uptime of the node)
- `VERSION` : version of kubernetes, We use k3s that's why the version is `v1.25.4+k3s1`