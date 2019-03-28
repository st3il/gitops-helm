## install flux ##

```
helm repo add weaveworks https://weaveworks.github.io/flux

helm install --name flux \
--set rbac.create=true \
--set helmOperator.create=true \
--set git.url=git@github.com:st3il/gitops-helm \
--set git.pollInterval="30s" \
--namespace flux \
weaveworks/flux
```

```
helm upgrade --reuse-values flux \
--set git.pollInterval="30s" \
weaveworks/flux
```