---
date: 2016-04-09T16:50:16+02:00
title: Kubernetes deployment
weight: 70
---

#### Compute deployments

```HCL
job "kubernetes" "deployment" {
    namespace = "nginx"
     config {
        tag = "app:nginx"
        count = 1
        chaos = "terminate"
    }
}
```
chaos config:
* *terminate*: Finds deployments with specified label and terminates them, *one by one*.
* *update*: Finds a single deployment and updates the number of replicas to the count parament.
