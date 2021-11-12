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
3. Test it

```
docker pull artifactory.xxx.local/anchore-inline-scan:latest
latest: Pulling from anchore-inline-scan
296e14ee2414: Already exists
356f18f3a935: Already exists
872030f417eb: Already exists
b91585f34683: Already exists
c53ddb9d433c: Already exists
0eab680bd6a6: Already exists
9fed99faba8e: Already exists
```
