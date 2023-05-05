---
date: 2016-04-09T16:50:16+02:00
title: GCP VMs instances
weight: 110
---

#### Compute instances

```HCL
job "gcp" "vm" {
    project = "my-awesome-company-project"
    region = "us-central1-a"
    config {
        tag = "env:prod"
        chaos = "terminate"
        count = 8
    }
}
```
chaos config:
* *terminate*: Finds compute VM instances with specified tag and destroys them.
* *reset*: Finds compute VM instances with specified tag and resets the instances.
* *stop*: Stops compute VM instances.