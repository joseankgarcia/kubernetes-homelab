# Hello Web

`hello-web` is a simple Nginx workload that is used to validate the initial MikroK8s cluster foundation. It was used to confirm that the cluster could deploy an application, expose it with NodePort, scale to 3 replicas, and schedule one pod on each node.

## Manifests

| File | Purpose |
|---|---|
| [`deployment.yaml`](/manifests/hello-web/deployment.yaml) | Defines the nginx workload, labels, container image, and replica count |
| [`service.yaml`](/manifests/hello-web/service.yaml) | Exposes the nginx pods using a NodePort service |

## Configuration Summary

| Setting | Value |
|---|---|
| Application name | `hello-web` |
| Container image | `nginx` |
| Replicas | `3` |
| Service type | `NodePort` |
| Container port | `80` |

## Verification

This workload was verified with:

- 3 replicas running
- one pod scheduled on each node
- NodePort service reachable from the control plane and both worker node IPs

## Related Assets
- ```Service Exposure```
 <br>  ![Service Exposure](/assets/hello-web/screenshots/microk8s-kubectl-get-svc-hello-web.png)
- ```Deployment Status``` <br>
  ![Deployment Status](/assets/hello-web/screenshots/microk8s-kubectl-get-deployment-hello-web.png)
- ```Pod Scheduler``` <br>
  ![Pod Schedule](/assets/hello-web/screenshots/microk8s-kubectl-get-pods--l-app=hello-web.png)
- ```Browser Verification``` <br>
  ![Browser Verification](/assets/hello-web/screenshots/welcome-to-nginx.png)
