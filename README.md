# cilium

https://artifacthub.io/packages/helm/cilium/cilium

Install cilium cli:
```bash
brew install cilium-cli
```

Add Cilium repo:
```bash
helm repo add cilium https://helm.cilium.io/
```

Install Cilium:
```bash
helm upgrade -i cilium cilium/cilium \
  --namespace kube-system
```
