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

## Current Status

### Completed

- [x] Created 3 Ubuntu Server VMs in Proxmox
- [x] Installed MicroK8s on all nodes
- [x] Joined 2 worker nodes to the control plane
- [x] Verified all 3 nodes are Ready
- [x] Deployed nginx test app
- [x] Exposed nginx using a NodePort service
- [x] Confirmed NodePort access from all 3 node IPs
- [x] Scaled nginx deployment to 3 replicas
- [x] Verified one nginx pod running on each node

### Planned

- [ ] Add ingress controller
- [ ] Add MetalLB for local load balancing
- [ ] Deploy app through ingress instead of only NodePort
- [ ] Add persistent storage test
- [ ] Test Kubernetes self-healing by deleting a pod
- [ ] Write first troubleshooting incident report
- [ ] Add Rancher UI for cluster visibility and workload management
- [ ] Deploy an app through Rancher UI
- [ ] Compare CLI-based deployment vs Rancher UI deployment
- [ ] Add monitoring dashboard
- [ ] Create final architecture diagram

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

## v1.0.0 Summary

The first working release of this homelab includes:

- 3-node MicroK8s cluster
- 1 control plane node
- 2 worker nodes
- nginx test deployment
- NodePort service exposure
- 3 nginx replicas
- one nginx pod scheduled on each node

## Verification Commands

```bash
microk8s kubectl get nodes
microk8s kubectl get pods -o wide
microk8s kubectl get deployment nginx-test
microk8s kubectl get svc nginx-test
