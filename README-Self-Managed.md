### Set the credentials
Set these with the information for your Elasticsearch cluster and your Kibana host.  Here are some examples

#### ELASTICSEARCH_HOSTS
1. A nodeGroup from the Elastic Elasticseach Helm Chart: 
    ["http://elasticsearch-master.default.svc.cluster.local:9200"]

1. foo 
    ["http://elasticsearch-master.default.svc.cluster.local:9200"]


#### ELASTICSEARCH_PASSWORD

```
changeme
```

#### ELASTICSEARCH_USERNAME

```
elastic
```

#### KIBANA_HOST

```
"http://kibana-kibana.default.svc.cluster.local:5601"
```

```
vi ELASTICSEARCH_HOSTS
vi ELASTICSEARCH_PASSWORD
vi ELASTICSEARCH_USERNAME
vi KIBANA_HOST
```
and create a secret in the Kubernetes system level namespace

```
kubectl create secret generic dynamic-logging \
  --from-file=./ELASTICSEARCH_HOSTS \
  --from-file=./ELASTICSEARCH_PASSWORD \
  --from-file=./ELASTICSEARCH_USERNAME \
  --from-file=./KIBANA_HOST \
  --namespace=kube-system
```

