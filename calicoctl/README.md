### 配置路径:
/etc/calico/calicoctl.cfg

---  
```
[root@master01 traefik]# calicoctl node status
Calico process is running.

IPv4 BGP status
+--------------+-------------------+-------+----------+-------------+
| PEER ADDRESS |     PEER TYPE     | STATE |  SINCE   |    INFO     |
+--------------+-------------------+-------+----------+-------------+
| 192.168.2.7  | node-to-node mesh | up    | 01:35:43 | Established |
| 192.168.2.11 | node-to-node mesh | up    | 01:53:54 | Established |
+--------------+-------------------+-------+----------+-------------+

IPv6 BGP status
No IPv6 peers found.
```
