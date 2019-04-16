### Set the credentials
Set these with the values from the http://cloud.elastic.co deployment

```
vi ELASTIC_CLOUD_ID
vi ELASTIC_CLOUD_AUTH
```
and create a secret in the Kubernetes system level namespace

```
kubectl create secret generic dynamic-logging \
  --from-file=./ELASTIC_CLOUD_AUTH \
  --from-file=./ELASTIC_CLOUD_ID \
  --namespace=kube-system
```

