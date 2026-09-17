# cilium

https://artifacthub.io/packages/helm/cilium/cilium

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
  --set k8sServicePort=6443 \
  --set hubble.relay.enabled=true \
  --set hubble.ui.enabled=true
```
