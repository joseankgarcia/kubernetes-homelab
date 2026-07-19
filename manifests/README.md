# Kubernetes Manifests

This directory contains sanitized Kubernetes manifests used in the homelab.

```text
manifests/
  application_example/
    example_deployment.yaml
    example_service.yaml
```

## Applications

| Application | Purpose                                                                                       | Path                    |
| ----------- | --------------------------------------------------------------------------------------------- | ----------------------- |
| `hello-web` | Nginx test workload used to verify deployment, NodePort exposure, scaling, and pod scheduling | [hello-web](/manifests/hello-web/) |


## Standards

* One folder per application or workload
* Manifests are sanitized before commiting
* Live cluster metadata such as `status`, `uid`, `resourceVersion`, and `managedFields` are removed
* Secrets, tokens, passwords, or private environment values are not commited
* Future services as separate folders under `manifests/`

