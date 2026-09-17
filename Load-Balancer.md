# Load Balancer



```
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
