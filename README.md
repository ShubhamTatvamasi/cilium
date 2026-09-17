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
  --namespace kube-system \
  --set ipam.mode=kubernetes \
  --set kubeProxyReplacement=true \
  --set k8sServiceHost=cilium-lab-control-plane \
  --set k8sServicePort=6443
```

> `k8sServiceHost`/`k8sServicePort` are required when `kubeProxyReplacement=true` and the
> kind cluster has no kube-proxy (`kubeProxyMode: none` in `kind-cilium.yaml`). Without them,
> Cilium tries to reach the apiserver via its ClusterIP, which isn't routable before Cilium
> itself is up — a chicken-and-egg deadlock that leaves cilium pods stuck in `Init:0/6`.
> The hostname matches the control-plane node name from `kind-cilium.yaml` / `kind create --name cilium-lab`,
> and resolves via kind's docker network DNS.
