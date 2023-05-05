---
date: 2016-04-09T16:50:16+02:00
title: AWS Autoscaler
weight: 20
---

#### Compute Autoscaling

```HCL
job "aws" "ec2_autoscaling" {
    region = "us-west-2"
    config {
        tag = "env:prod"
        chaos = "update"
        count = 6
    }
}
```
chaos config:
* *terminate*: Finds autoscaling groups with specified tag and force deletes them.
* *update*: Finds a single autoscaling group with specified tag and sets the desired and maximum states to the count parameter, while at the same time the minimum state is configured to 0
* *desired*: Sets the desired capacity, not modifying the other states (minimum and maximum). The desired capacity has to be equal or below the maximum capacity with this chaos action.

