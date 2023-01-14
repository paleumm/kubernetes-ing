# Basic Components

[EN](./README-EN.md)/[TH](./README.md)

อันนี้รูปส่วนประกอบของ K8S Cluster แบบคร่าวๆ เอามาจาก[นี่](https://www.trendmicro.com/vinfo/us/security/news/security-technology/the-basics-of-keeping-your-kubernetes-cluster-secure-part-1)
![](https://documents.trendmicro.com/images/TEx/articles/diagram-of-a-Kubernetes-cluster-and-its-components.jpg) 

## Nodes

ถ้าอยากดูว่า Cluster ของเรามี node อะไรบ้างให้ใช้คำสั่ง
```bash
kubectl get nodes
```
Output จะประมาณนี้
```
NAME      STATUS   ROLES                  AGE    VERSION
ichiban   Ready    control-plane,master   2d6h   v1.25.4+k3s1
niban     Ready    <none>                 2d6h   v1.25.4+k3s1
```

- `NAME` : ชื่อของแต่ละ node
- `STATUS` : สถานะของ node นั้นๆ มี Ready, NotReady หรือ SchedulingDisabled ส่วนที่เหลือก็ดูได้ที่ [official document](https://kubernetes.io/docs/concepts/overview/)
- `ROLES` : บอกว่า node นั้นมีหน้าที่อะไร อย่างในตัวอย่าง control-plane,master โดยจะทำหน้าที่เช่นการกำหนดเรื่องการ Scheduling ให้ Cluster ส่วน `<none>` ก็คือเป็น worker node
- `AGE` : บอกว่า node นั้นมีอายุเท่าไหร่ (นับจากตอนสร้าง ไม่ได้นับ uptime)
- `VERSION` : version ของ kubernetes ที่ใช้ อย่างในตัวอย่างใช้ k3s เลยกลายเป็น `v1.25.4+k3s1`

ในส่วนของคำสั่ง `Kubectl get nodes` เป็นคำสั่งที่อยู่ในหมวด `get` ซึ่งจะตามด้วย resource type เช่น `node, pod, service` 
นอกจากคำสั่ง `get` แล้ว เราสามารถใช้คำสั่ง `describe` เพื่อให้ตัว api แสดงผลเกี่ยวกับ resource type ที่เรากำหนดแบบละเอียดยิ่งขึ้น 

```bash
kubectl describe node ichiban
```

ซึ่งคำสั่งนี้จะแสดงผลรายละเอียดต่างของ node ichiban ซึ่ง ichiban เป็นชื่อ node ที่ผมกำหนดขึ้นมาใน Cluster ผม ดังนั้นชื่อ node ของแต่ละคนจะแตกต่างกันไป สามารถใช้คำสั่ง get node เพื่อดูได้ว่าชื่อ node ของเรามีอะไรบ้าง ไม่งั้นจะเจอ error ประมาณว่า 
`Error from server (NotFound): nodes "mai-ru" not found`
