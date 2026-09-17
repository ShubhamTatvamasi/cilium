# API resources

Here’s a clean table of the **Cilium-specific Kubernetes API resources** from your cluster output. 

| Resource                           | Short Name                                   | API Version          | Namespaced | Kind                           | Purpose                                              |
| ---------------------------------- | -------------------------------------------- | -------------------- | ---------- | ------------------------------ | ---------------------------------------------------- |
| `ciliumcidrgroups`                 | `ccg`                                        | `cilium.io/v2`       | No         | CiliumCIDRGroup                | Groups CIDRs for use in Cilium network policies      |
| `ciliumclusterwidenetworkpolicies` | `ccnp`                                       | `cilium.io/v2`       | No         | CiliumClusterwideNetworkPolicy | Cluster-wide network and security policies           |
| `ciliumendpoints`                  | `cep`, `ciliumep`                            | `cilium.io/v2`       | Yes        | CiliumEndpoint                 | Represents a pod/workload endpoint managed by Cilium |
| `ciliumidentities`                 | `ciliumid`                                   | `cilium.io/v2`       | No         | CiliumIdentity                 | Represents security identities assigned to workloads |
| `ciliuml2announcementpolicies`     | `l2announcement`                             | `cilium.io/v2alpha1` | No         | CiliumL2AnnouncementPolicy     | Controls L2 announcements for services               |
| `ciliumloadbalancerippools`        | `ippools`, `ippool`, `lbippool`, `lbippools` | `cilium.io/v2`       | No         | CiliumLoadBalancerIPPool       | Defines IP pools used for LoadBalancer services      |
| `ciliumnetworkpolicies`            | `cnp`, `ciliumnp`                            | `cilium.io/v2`       | Yes        | CiliumNetworkPolicy            | Namespace-scoped network and security policies       |
| `ciliumnodeconfigs`                | —                                            | `cilium.io/v2`       | Yes        | CiliumNodeConfig               | Configures Cilium behavior for selected nodes        |
| `ciliumnodes`                      | `cn`, `ciliumn`                              | `cilium.io/v2`       | No         | CiliumNode                     | Represents Cilium-managed Kubernetes nodes           |
| `ciliumpodippools`                 | `cpip`                                       | `cilium.io/v2alpha1` | No         | CiliumPodIPPool                | Defines pools from which pod IPs can be allocated    |

### Quick grouping

| Category                    | Resources                                               |
| --------------------------- | ------------------------------------------------------- |
| **Network Policy**          | `CiliumNetworkPolicy`, `CiliumClusterwideNetworkPolicy` |
| **Identity & Endpoint**     | `CiliumIdentity`, `CiliumEndpoint`                      |
| **Node**                    | `CiliumNode`, `CiliumNodeConfig`                        |
| **IPAM**                    | `CiliumPodIPPool`, `CiliumLoadBalancerIPPool`           |
| **L2 / Service Networking** | `CiliumL2AnnouncementPolicy`                            |
| **CIDR Management**         | `CiliumCIDRGroup`                                       |

**Useful commands:**

```bash
kubectl get cnp -A
kubectl get ccnp
kubectl get cep -A
kubectl get ciliumidentity
kubectl get ciliumnodes
kubectl get ciliumloadbalancerippools
kubectl get ciliumpodippools
kubectl get ciliuml2announcementpolicies
kubectl get ciliumcidrgroups
kubectl get ciliumnodeconfigs -A
```

Note that the exact resources shown are **from your cluster's `kubectl api-resources` output**, so this table reflects the Cilium version/features currently installed there. 
