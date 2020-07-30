### 通过设置环境变量访问etcd服务


```
[root@master01 traefik]# etcdctl member list
e99d560084d446c8, started, master01.dev.com, https://192.168.2.10:2380, https://192.168.2.10:2379, false
```

---
```
[root@master01 traefik]# etcdctl --prefix --keys-only=true get /
/registry/apiextensions.k8s.io/customresourcedefinitions/bgpconfigurations.crd.projectcalico.org

/registry/apiextensions.k8s.io/customresourcedefinitions/bgppeers.crd.projectcalico.org

/registry/apiextensions.k8s.io/customresourcedefinitions/blockaffinities.crd.projectcalico.org

/registry/apiextensions.k8s.io/customresourcedefinitions/clusterinformations.crd.projectcalico.org

/registry/apiextensions.k8s.io/customresourcedefinitions/felixconfigurations.crd.projectcalico.org
...
```
