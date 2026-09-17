# Load Balancer

Get the nodes details:
```bash
kubectl get nodes -o wide
```

Create an IP pool:
```yaml
kubectl create -f - << EOF
apiVersion: cilium.io/v2
kind: CiliumLoadBalancerIPPool
metadata:
  name: default-pool
spec:
  blocks:
    - cidr: 172.19.0.10/32
EOF
```

---

Deploy nginx:
```bash
kubectl create deployment nginx --image=nginx:alpine
kubectl expose deployment nginx --port=80 --name=nginx --type=LoadBalancer
```

Get inside docker node:
```bash
docker exec -it cilium-lab-worker2 bash
```

test connection:
```
curl 172.19.0.10
```

Cleanup:
```bash
kubectl delete deploy/nginx svc/nginx
```
