# API resources

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
