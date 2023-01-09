# Prerequisites

1. **ต้องมี** K8S cluster ก่อน
    มีหลายวิธีที่เราสามารถ setup K8S Cluster ได้ เลยไม่มี tutorial ให้ดู ดังนั้นจะแปะลิงค์ไว้ให้ละกัน
    - [minikube](https://www.digitalocean.com/community/tutorials/how-to-use-minikube-for-local-kubernetes-development-and-testing) แนะนำ มันลงง่าย
    - [kubespray](https://github.com/kubernetes-sigs/kubespray) ถ้าลงอันนี้ได้ repo ผมคงไม่มีประโยชน์กับคุณเท่าไหร่แล้ว (ล้อเล่นนะ)
    - [kubeadm](https://kubernetes.io/docs/setup/production-environment/tools/kubeadm/create-cluster-kubeadm/) ไม่รู้เหมือนกัน ไม่เคยใช้
    - [k3s](https://docs.k3s.io/installation) อันนี้ lightweight แต่จะมีบาง features ที่ไม่มีเหมือน k8s ปกติ
2.  สามารถใช้คำสั่ง `kubectl` ได้
    ถ้าลองรัน `kubectl get nodes` แล้วได้ output เป็นชื่อ node แปลว่าผ่าน

3. (optional) ลง Extension Kubernetes ใน vscode (ถ้าใครใช้)