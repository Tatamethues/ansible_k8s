## Coredns with cilium

### Readiness probe failed: HTTP probe failed with statuscode: 503
```
sudo iptables -F
```

### coredns [ERROR] plugin/errors: 2 read udp 10.244.235.249:55567->10.96.0.10:53: i/o timeout 

```
iptables -P INPUT ACCEPT
iptables -P FORWARD ACCEPT
iptables -P OUTPUT ACCEPT
iptables -F

```