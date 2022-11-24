---
date: 2016-04-09T16:50:16+02:00
title: K8s
---

## Environment

In the next theorical environment, we have a inventory app that is running on k8s, the hypothesis is that our customers are able to get products with no problem even if our app gets scale down or up.

## Experiment

Create a new chaos experiment file called `inventory-config.hcl` 


```HCL
app = "inventory app"
description = "Chaos Experiment for inventory app, check if customers are able to get products in cart" 

job "kubernetes" "pod" {
    namespace = "inventory-app"
    config {
        tag = "app:inventory-prod"  
        chaos = "terminate"         
        count = 5                   
    }
}
```
The previous job will find 5 pods with label *app:inventory-prod* and terminate those. 

In the same experiment, let's check how does the cluster behaves with such rapid changes


```HCL
job "kubernetes" "deployment" {
    namespace = "inventory-app"
    config {
        tag = "app:inventory-prod" 
        chaos = "update"
        count = 20
    }
}
```
This job will increase to *20* the number of pods of the *deployment* with label *app:inventory-prod*