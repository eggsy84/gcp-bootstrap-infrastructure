# gcp-bootstrap-infrastructure
Starting point for the GCP and K8S Continuous Delivery Seed

## Introduction

Full details on the code and its usage can be found on the corresponding GCP blog:

https://medium.com/google-cloud/zero-to-continuous-delivery-with-google-cloud-platform-8e3bf1312fb5#.87imb0tqq


## Instructions

The bootstrap script takes the following arguments:

1) **GCP_PROJECT** The name of your Google Cloud Project

2) **GCP_ZONE** The GCP zone for your GKE cluster

3) **GCP_MACHINE_TYPE** The GCP machine type

4) **NUM_NODES** The number of nodes that should make up your cluster

```
cd bootstrap && sh deploy.sh {project_name} {zone} {machine-type} {number-of-nodes} {service_account_key}
```

For example

```
cd bootstrap && \
sh deploy.sh \
my-gcp-project \
europe-west1-b \
n1-standard-2 \
1 \
/somedir/docker-meetup-a08ce8d4d8bc.json
```

The script will ask you to log in to your Google Account.

Once verified it will continue to create a GKE cluster and in turn deploy
a Jenkins master container on to the cluster.

The console will then confirm the actions it is about to take and ask you to press any key to continue.

## IMPORTANT NOTE

This script will provision infrastructure on Google Cloud and you may incur costs for having active infrastructure within the platform
