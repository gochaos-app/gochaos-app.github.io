---
date: 2016-04-09T16:50:16+02:00
title: Kubernetes pods
weight: 60
---

#### Compute pods 

```HCL
job "kubernetes" "pod" {
    namespace = "default"
     config {
        tag = "app:nginx"
        count = 1
        chaos = "terminate"
    }
}
```
chaos config:
* *terminate*: Finds pods with specified label and terminates them, *one by one*.
* *terminateAll*: Terminates entire collection of pods at the *same time*. Parameter *count* will be 
ignored in this operation, unless is 0, which will skip the job. Be careful with this configuration. 

^^ ***terminateAll*** This needs to change, terminateAll should delete at the same time every pod ***found*** not entire collection, deletecolletion was easier to implement, and make count boolean, either 0 or 1, however cannot ignore parameters like that. This can be achieved with either go routines or functions.