```
kubectl create secret docker-registry image-pull-secret \
  -n default \
  --docker-server=docker.io \
  --docker-username=devopstales \
  --docker-password=devopstales \
  --docker-email=devopstales.mydomain.intra

kubectl patch serviceaccount default \
  -p "{\"imagePullSecrets\": [{\"name\": \"image-pull-secret\"}]}" \
  -n default
```
