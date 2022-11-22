---
date: 2016-04-09T16:50:16+02:00
title: Kubernetes daemonsets
weight: 80
---

#### Compute deployments

```HCL
job "kubernetes" "daemonSet" {
    namespace = "default"
     config {
        tag = "k8s-app:fluentd-logging"
        count = 1
        chaos = "terminate"
    }
}
```
chaos config:
* *terminate*: Finds daemonSet with specified label and terminates those found.
