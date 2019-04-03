## install flux ##

```
helm repo add weaveworks https://weaveworks.github.io/flux
```
add with custom chartmuseum
```
helm install --name flux \
    --set rbac.create=true \
    --set helmOperator.create=true \
    --set helmOperator.createCRD=false \
    --set git.url=git@github.com:st3il/gitops-helm \
    --set git.pollInterval="30s" \
    --namespace flux \
    --set helmOperator.configureRepositories.enable=true \
weaveworks/flux
```
add with public chart in repo
```
helm install --name flux \
    --set rbac.create=true \
    --set helmOperator.create=true \
    --set helmOperator.createCRD=false \
    --set git.url=git@github.com:st3il/gitops-helm \
    --set git.pollInterval="30s" \
    --namespace flux \
weaveworks/flux
```
update flux parameters
```
helm upgrade --reuse-values flux \
--set git.pollInterval="30s" \
weaveworks/flux
```
delete flux
```
helm del --purge flux
```