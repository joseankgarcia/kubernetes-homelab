# Kubernetes Homelab

A 3-node Kubernetes homelab built on Ubuntu Server using MicroK8s and Proxmox.

This project is focused on learning and documenting core Kubernetes operations: cluster setup, worker node joining, workload deployment, service exposure, scaling, scheduling, and future troubleshooting.

## Overview

The lab currently runs a 3-node MicroK8s cluster with one control plane node and two worker nodes. A test nginx workload has been deployed, exposed through NodePort, scaled to 3 replicas, and verified across all three nodes.

## Lab Environment

| Hostname | Role | Platform | OS | CPU | RAM | Disk |
|---|---|---|---|---|---|---|
| `k8s-cp-01` | Control plane node | Proxmox VM | Ubuntu Server | 2 cores | 4 GB | 40 GB |
| `k8s-w-01` | Worker node | Proxmox VM | Ubuntu Server | 2 cores | 4 GB | 40 GB |
| `k8s-w-02` | Worker node | Proxmox VM | Ubuntu Server | 2 cores | 4 GB | 40 GB |

## Version Milestones

| Version | Focus | Status |
|---|---|---|
| `v1.0.0` | Initial working 3-node MicroK8s cluster | Complete |
| `v1.1.0` | Ingress and MetalLB local load balancing | Planned |
| `v1.2.0` | Persistent storage test | Planned |
| `v1.3.0` | Self-healing test and incident writeup | Planned |
| `v1.4.0` | Basic monitoring dashboard | Planned |
| `v1.5.0` | Rancher UI and cluster management | Planned |
| `v1.6.0` | GitOps deployment workflow | Planned |
| `v1.7.0` | Centralized logging | Planned |
| `v1.8.0` | Docker-to-Kubernetes app migration | Planned |
| `v1.9.0` | Backup and restore testing | Planned |

## Current Stable Baseline

`v1.0.0` is the first stable working baseline of this Kubernetes homelab.

This release includes
- 3-node MicroK8s cluster running on Ubuntu Server VMs in Proxmox
- 1 control plane node and 2 worker nodes.
- A test nginx workload was deployed as `hello-web`
- Exposed through a NodePort service
- Scaled to 3 replicas
- Verified with one pod running on each node.

Sanitized Kubernetes manifests for the deployment and service are included in this repository. Full release details are available in the GitHub Releases page under `v1.0.0`.

## Verification Commands

```bash
microk8s kubectl get nodes
microk8s kubectl get pods -o wide
microk8s kubectl get deployment nginx-test
microk8s kubectl get svc nginx-test
```





