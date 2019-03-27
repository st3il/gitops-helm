## steps ##

```
helm install --name flux \
--set git.url=git@github.com:st3il/gitops-helm \
--namespace flux \
weaveworks/flux
```