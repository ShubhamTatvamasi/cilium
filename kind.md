# Kind

Install 3 nodes Kind cluster:
```bash
kind create cluster \
  --name cilium-lab \
  --config kind-cilium.yaml
```

Delete Kind cluster:
```bash
kind delete cluster \
  --name cilium-lab
```
