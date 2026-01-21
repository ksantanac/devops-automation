
# Relatório de Informações do Cluster AKS

## 1. Informações do Cluster

- **Control Plane:** https://aks-free-c-aks-free-rg-6fa70b-s88yjnjw.hcp.eastus2.azmk8s.io:443
- **CoreDNS:** https://aks-free-c-aks-free-rg-6fa70b-s88yjnjw.hcp.eastus2.azmk8s.io:443/api/v1/namespaces/kube-system/services/kube-dns:dns/proxy
- **Metrics-server:** https://aks-free-c-aks-free-rg-6fa70b-s88yjnjw.hcp.eastus2.azmk8s.io:443/api/v1/namespaces/kube-system/services/https:metrics-server:/proxy

## 2. Nós (Nodes)

### Resumo dos Nós

| NOME                               | STATUS | ROLES  | IDADE | VERSÃO  | IP INTERNO   | IP EXTERNO | OS-IMAGE           | KERNEL-VERSION    | CONTAINER-RUNTIME     |
| ---------------------------------- | ------ | ------ | ----- | ------- | ------------ | ---------- | ------------------ | ----------------- | --------------------- |
| aks-nodepool1-90986754-vmss000000 | Ready  | <none> | 27m   | v1.33.5 | 10.224.0.4   | <none>     | Ubuntu 22.04.5 LTS | 5.15.0-1102-azure | containerd://1.7.29-1 |

### Detalhes do Nó: aks-nodepool1-90986754-vmss000000

- **Sistema Operacional:** Ubuntu 22.04.5 LTS
- **Versão do Kernel:** 5.15.0-1102-azure
- **Versão do Kubelet:** v1.33.5
- **Container Runtime:** containerd://1.7.29-1
- **Recursos:**
  - **CPU:** 2
  - **Memória:** 8129932Ki
  - **Pods:** 250
- **Recursos Alocáveis:**
  - **CPU:** 1900m
  - **Memória:** 5930380Ki
  - **Pods:** 250
- **Condições:**
  - **Ready:** True
  - **MemoryPressure:** False
  - **DiskPressure:** False
  - **PIDPressure:** False

## 3. Namespaces

| NOME            | STATUS | IDADE |
| --------------- | ------ | ----- |
| default         | Active | 28m   |
| kube-node-lease | Active | 28m   |
| kube-public     | Active | 28m   |
| kube-system     | Active | 28m   |

## 4. Workloads

### Pods

| NAMESPACE   | NOME                                           | READY | STATUS  | RESTARTS    | IDADE | IP           | NÓ                                |
| ----------- | ---------------------------------------------- | ----- | ------- | ----------- | ----- | ------------ | --------------------------------- |
| default     | java-api-deployment-54cf7bbd85-5j62l           | 1/1   | Running | 0           | 22m   | 10.244.0.124 | aks-nodepool1-90986754-vmss000000 |
| default     | java-api-deployment-54cf7bbd85-dlzqf           | 1/1   | Running | 0           | 22m   | 10.244.0.134 | aks-nodepool1-90986754-vmss000000 |
| kube-system | ama-logs-cx5s7                                 | 3/3   | Running | 1 (17m ago) | 26m   | 10.244.0.138 | aks-nodepool1-90986754-vmss000000 |
| kube-system | ama-logs-rs-69859449dc-7hl4j                   | 2/2   | Running | 0           | 26m   | 10.244.0.205 | aks-nodepool1-90986754-vmss000000 |
| kube-system | azure-cns-b668p                                | 1/1   | Running | 0           | 27m   | 10.224.0.4   | aks-nodepool1-90986754-vmss000000 |
| kube-system | azure-ip-masq-agent-c452d                      | 1/1   | Running | 0           | 27m   | 10.224.0.4   | aks-nodepool1-90986754-vmss000000 |
| kube-system | cloud-node-manager-5k4z8                       | 1/1   | Running | 0           | 27m   | 10.224.0.4   | aks-nodepool1-90986754-vmss000000 |
| kube-system | coredns-5b5b89b58c-7k9xd                       | 1/1   | Running | 0           | 28m   | 10.244.0.55  | aks-nodepool1-90986754-vmss000000 |
| kube-system | coredns-5b5b89b58c-mkf6r                       | 1/1   | Running | 0           | 27m   | 10.244.0.140 | aks-nodepool1-90986754-vmss000000 |
| kube-system | coredns-autoscaler-67d9d668db-rgjmn            | 1/1   | Running | 0           | 28m   | 10.244.0.212 | aks-nodepool1-90986754-vmss000000 |
| kube-system | csi-azuredisk-node-4mphh                       | 3/3   | Running | 0           | 27m   | 10.224.0.4   | aks-nodepool1-90986754-vmss000000 |
| kube-system | csi-azurefile-node-fhw58                       | 3/3   | Running | 0           | 27m   | 10.224.0.4   | aks-nodepool1-90986754-vmss000000 |
| kube-system | konnectivity-agent-79ddc5cd56-fmvjc            | 1/1   | Running | 0           | 28m   | 10.244.0.2   | aks-nodepool1-90986754-vmss000000 |
| kube-system | konnectivity-agent-79ddc5cd56-sxlrp            | 1/1   | Running | 0           | 27m   | 10.244.0.243 | aks-nodepool1-90986754-vmss000000 |
| kube-system | konnectivity-agent-autoscaler-6ff7779788-jx4l8 | 1/1   | Running | 0           | 28m   | 10.244.0.230 | aks-nodepool1-90986754-vmss000000 |
| kube-system | kube-proxy-qcqhh                               | 1/1   | Running | 0           | 27m   | 10.224.0.4   | aks-nodepool1-90986754-vmss000000 |
| kube-system | metrics-server-5744f855b8-2vf86                | 2/2   | Running | 0           | 27m   | 10.244.0.86  | aks-nodepool1-90986754-vmss000000 |
| kube-system | metrics-server-5744f855b8-tq9hg                | 2/2   | Running | 0           | 27m   | 10.244.0.223 | aks-nodepool1-90986754-vmss000000 |

### Deployments

| NAMESPACE   | NOME                          | READY | UP-TO-DATE | AVAILABLE | IDADE |
| ----------- | ----------------------------- | ----- | ---------- | --------- | ----- |
| default     | java-api-deployment           | 2/2   | 2          | 2         | 22m   |
| kube-system | ama-logs-rs                   | 1/1   | 1          | 1         | 27m   |
| kube-system | coredns                       | 2/2   | 2          | 2         | 28m   |
| kube-system | coredns-autoscaler            | 1/1   | 1          | 1         | 28m   |
| kube-system | konnectivity-agent            | 2/2   | 2          | 2         | 28m   |
| kube-system | konnectivity-agent-autoscaler | 1/1   | 1          | 1         | 28m   |
| kube-system | metrics-server                | 2/2   | 2          | 2         | 28m   |

### Services

| NAMESPACE   | NOME             | TIPO         | CLUSTER-IP   | EXTERNAL-IP  | PORT(S)       | IDADE |
| ----------- | ---------------- | ------------ | ------------ | ------------ | ------------- | ----- |
| default     | java-api-service | LoadBalancer | 10.0.176.156 | 4.152.203.74 | 80:30116/TCP  | 22m   |
| default     | kubernetes       | ClusterIP    | 10.0.0.1     | <none>       | 443/TCP       | 29m   |
| kube-system | kube-dns         | ClusterIP    | 10.0.0.10    | <none>       | 53/UDP,53/TCP | 28m   |
| kube-system | metrics-server   | ClusterIP    | 10.0.6.144   | <none>       | 443/TCP       | 28m   |

## 5. Autoscaling

### Horizontal Pod Autoscalers (HPAs)

Nenhum recurso encontrado.

## 6. Armazenamento

### Persistent Volumes (PVs)

Nenhum recurso encontrado.

### Persistent Volume Claims (PVCs)

Nenhum recurso encontrado.
