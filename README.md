# srs-aks-template

**IMPORTANT NOTE**: This repository is depreacated and archived, please use [srs-cdk](https://github.com/ossrs/srs-cdk) instead. CDK is the future of default and recommended deployment for SRS and Oryx.

![](http://ossrs.net/gif/v1/sls.gif?site=github.com&path=/tmpl/k8s/aks/ossrs/srs-aks-template)
[![](https://github.com/ossrs/srs-aks-template/actions/workflows/azure-kubernetes-service.yml/badge.svg)](https://github.com/ossrs/srs-aks-template/actions/workflows/azure-kubernetes-service.yml)

Template repository for deploying SRS to [AKS(Azure Kubernetes Service)](https://docs.microsoft.com/en-us/azure/aks/).

## Usage

**Step 1:** Create AKS cluster and user:

1. Create a [subscription](https://portal.azure.com/?quickstart=true#blade/Microsoft_Azure_Billing/SubscriptionsBlade) and [resource group](https://portal.azure.com/?quickstart=true#blade/HubsExtension/BrowseResourceGroups).
1. Create a K8s cluster by [AKS](https://docs.microsoft.com/en-us/azure/aks/kubernetes-walkthrough-portal), check by command `kubectl get namespace`
1. Create a new [CREDENTIALS](https://docs.microsoft.com/en-us/azure/aks/kubernetes-action#create-a-service-principal) with `subscription` and `resource group`.

**Step 2:** Click the <kbd>Use this template</kbd> to create your repository, then set the [secrets](https://github.com/ossrs/srs-aks-template/settings/secrets/actions):

1. `AZURE_CREDENTIALS` is the [CREDENTIALS](https://docs.microsoft.com/en-us/azure/aks/kubernetes-action#create-a-service-principal).
1. `RESOURCE_GROUP` is the [resource group](https://portal.azure.com/?quickstart=true#blade/HubsExtension/BrowseResourceGroups).
1. `CLUSTER_NAME` is the name of [AKS](https://docs.microsoft.com/en-us/azure/aks/kubernetes-walkthrough-portal) cluster.

**Step 3:** Run <kbd>Actions</kbd> to deploy to your K8s, for example, if your external IP is `52.149.197.10`:

* Website is http://52.149.197.10:8080
* Publish RTMP to rtmp://52.149.197.10/live/livestream
* Play RTMP from rtmp://52.149.197.10/live/livestream
* Play HTTP-FLV from http://52.149.197.10:8080/live/livestream.flv
* Play HLS from http://52.149.197.10:8080/live/livestream.m3u8

Try to motify the [srs.yaml](srs.yaml), then push to your repository, your K8s will be updated automatically.

