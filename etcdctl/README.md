## 通过设置环境变量访问etcd服务

+ 查看etcd成员
```
[root@master01 traefik]# etcdctl member list
e99d560084d446c8, started, master01.dev.com, https://192.168.2.10:2380, https://192.168.2.10:2379, false
```  
---
+ 查看所有的key
```
[root@master01 traefik]# etcdctl --prefix --keys-only=true get /
/registry/apiextensions.k8s.io/customresourcedefinitions/bgpconfigurations.crd.projectcalico.org

/registry/apiextensions.k8s.io/customresourcedefinitions/bgppeers.crd.projectcalico.org

/registry/apiextensions.k8s.io/customresourcedefinitions/blockaffinities.crd.projectcalico.org

/registry/apiextensions.k8s.io/customresourcedefinitions/clusterinformations.crd.projectcalico.org

/registry/apiextensions.k8s.io/customresourcedefinitions/felixconfigurations.crd.projectcalico.org
...
```  
---  
+ 获取所有namespaces
```
[root@master01 traefik]# etcdctl get /registry/namespaces --prefix -w json | jq .
{
  "header": {
    "cluster_id": 5248883760918225000,
    "member_id": 16833705542409275000,
    "revision": 342035,
    "raft_term": 3
  },
  "kvs": [
    {
      "key": "L3JlZ2lzdHJ5L25hbWVzcGFjZXMvZGVmYXVsdA==",
      "create_revision": 152,
      "mod_revision": 152,
      "version": 1,
      "value": "azhzAAoPCgJ2MRIJTmFtZXNwYWNlErIBCpcBCgdkZWZhdWx0EgAaACIAKiQ3YzVkOTZmMi1lOGE0LTQ4ZmItOTUzNS1mZDVlOWE3NTI3M2EyADgAQggI1Kr/+AUQAHoAigFPCg5rdWJlLWFwaXNlcnZlchIGVXBkYXRlGgJ2MSIICNSq//gFEAAyCEZpZWxkc1YxOh0KG3siZjpzdGF0dXMiOnsiZjpwaGFzZSI6e319fRIMCgprdWJlcm5ldGVzGggKBkFjdGl2ZRoAIgA="
    },
    {
      "key": "L3JlZ2lzdHJ5L25hbWVzcGFjZXMva3ViZS1ub2RlLWxlYXNl",
      "create_revision": 6,
      "mod_revision": 6,
      "version": 1,
      "value": "azhzAAoPCgJ2MRIJTmFtZXNwYWNlEroBCp8BCg9rdWJlLW5vZGUtbGVhc2USABoAIgAqJDkxMjI0MjllLWQ1YWEtNDNhNC04YzVlLTNmOGM3ZjE4MDk0NzIAOABCCAjTqv/4BRAAegCKAU8KDmt1YmUtYXBpc2VydmVyEgZVcGRhdGUaAnYxIggI06r/+AUQADIIRmllbGRzVjE6HQobeyJmOnN0YXR1cyI6eyJmOnBoYXNlIjp7fX19EgwKCmt1YmVybmV0ZXMaCAoGQWN0aXZlGgAiAA=="
    },
    {
      "key": "L3JlZ2lzdHJ5L25hbWVzcGFjZXMva3ViZS1wdWJsaWM=",
      "create_revision": 5,
      "mod_revision": 5,
      "version": 1,
      "value": "azhzAAoPCgJ2MRIJTmFtZXNwYWNlErYBCpsBCgtrdWJlLXB1YmxpYxIAGgAiACokNTg1ODg4OTUtNWExNC00ZjhkLWE1M2QtMTUxMDE5MjQzZmQwMgA4AEIICNOq//gFEAB6AIoBTwoOa3ViZS1hcGlzZXJ2ZXISBlVwZGF0ZRoCdjEiCAjTqv/4BRAAMghGaWVsZHNWMTodCht7ImY6c3RhdHVzIjp7ImY6cGhhc2UiOnt9fX0SDAoKa3ViZXJuZXRlcxoICgZBY3RpdmUaACIA"
    },
    {
      "key": "L3JlZ2lzdHJ5L25hbWVzcGFjZXMva3ViZS1zeXN0ZW0=",
      "create_revision": 4,
      "mod_revision": 4,
      "version": 1,
      "value": "azhzAAoPCgJ2MRIJTmFtZXNwYWNlErYBCpsBCgtrdWJlLXN5c3RlbRIAGgAiACokNTg3MTc2OGItNTI2OS00NWM1LTg2MDQtNGU2OGE3Njg0NWQ1MgA4AEIICNOq//gFEAB6AIoBTwoOa3ViZS1hcGlzZXJ2ZXISBlVwZGF0ZRoCdjEiCAjTqv/4BRAAMghGaWVsZHNWMTodCht7ImY6c3RhdHVzIjp7ImY6cGhhc2UiOnt9fX0SDAoKa3ViZXJuZXRlcxoICgZBY3RpdmUaACIA"
    }
  ],
  "count": 4
}
```
