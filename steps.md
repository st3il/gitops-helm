## steps ##

```
helm install --name flux \
--set rbac.create=true \
--set helmOperator.create=true \
--set git.url=git@github.com:st3il/gitops-helm \
--namespace flux \
weaveworks/flux
```