# Load Balancer


Create an IP pool:
```yaml
kubectl create -f - << EOF
apiVersion: cilium.io/v2
kind: CiliumLoadBalancerIPPool
metadata:
  name: default-pool
spec:
  blocks:
    - cidr: 172.19.0.3/32
EOF
```

---

Test:
```bash
kubectl create deployment nginx --image=nginx:alpine
kubectl expose deployment nginx --port=80 --name=nginx --type=LoadBalancer
```

Cleanup:
```bash
kubectl delete deploy/nginx svc/nginx
```
