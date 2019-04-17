There are four README files here:

1. README-Main.md
1. README-Cloud.md
1. README-Self-Managed.md
1. This file, README.md

README-Cloud and README-Self-Managed cover creating Kubernetes secrets with the location and authentication information for your Elasticsearch cluster and Kibana instance.


# Introduction

foo

# Authorization
Create a cluster level role binding so that you can manipulate the system level namespace

```
kubectl create clusterrolebinding cluster-admin-binding \
 --clusterrole=cluster-admin --user=<your email associated with the Cloud provider account>
```

# Clone the YAML files
Either clone the entire Elastic examples repo or use the wget commands in download.txt:

```
mkdir MonitoringKubernetes
cd MonitoringKubernetes
wget https://raw.githubusercontent.com/elastic/examples/master/MonitoringKubernetes/download.txt
sh download.txt
```

OR

```
git clone https://github.com/elastic/examples.git
cd examples/MonitoringKubernetes
```

# Elasticsearch and Kibana

At this point you will need to have the URL(s) and credentials for an existing Elasticsearch cluster and Kibana server, or deploy Elasticsearch and Kibana.

## Decide if you will use the managed service, Elasticsearch Service in Elastic Cloud, or use self managed Elasticsearch and Kibana either in your Kubernetes cluster (with the Elastic Helm Charts), or outside of your Kubernetes Cluster with files from the Elastic download page.  You can use any of these three methods, and the Beats will send data to any of them.

### Managed service: 
Set the credentials and create the Kubernetes secret as detailed in README-Cloud.md

### Self managed: 
Deploy in k8s via Helm Charts, or downloaded files running on servers, or running on your own workstation.  Set the credentials and create the Kubernetes secret as detailed in README-Self-Managed.md

