# k8sProxy

Simple example how particular docker registries (paths) can be exposed/filtered using k8s nginx ingress.

Example for Anchore

How to:
1. define env vars like:

```bash
export UPSTREAM=artifactory.xxx
export FQDN=artifactory.xxx.local
export BASE=docker-images/something
```

2. Apply manifests:

```bash
cat ingress.yaml  service.yaml  | envsubst | kubectl apply -n default -f  -
```
