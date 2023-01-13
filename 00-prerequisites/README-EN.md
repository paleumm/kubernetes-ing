# Prerequisites

[EN](./README-EN.md)/[TH](./README.md)

1.  K8S cluster **must** be configured
    There are several ways to set up K8S Cluster, but this repository will not cover them, so I will provide some documentation on how to do so. 
    - [minikube](https://www.digitalocean.com/community/tutorials/how-to-use-minikube-for-local-kubernetes-development-and-testing) recommended for your computer, laptop
    - [kind](https://kind.sigs.k8s.io/docs/user/quick-start/) easy to install
    - [kubespray](https://github.com/kubernetes-sigs/kubespray) easy but hard to understand
    - [kubeadm](https://kubernetes.io/docs/setup/production-environment/tools/kubeadm/create-cluster-kubeadm/) never use this, no comment
    - [k3s](https://docs.k3s.io/installation) lightweight k8s, don't have some features that have in k8s (raspberry pi recommended)
2.  can use the `kubectl` 
    if you run `kubectl get nodes` you should got the `nodes` as output.

3. (optional) Kubernetes extension in vscode