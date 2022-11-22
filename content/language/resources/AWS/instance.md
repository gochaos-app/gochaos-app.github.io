---
date: 2016-04-09T16:50:16+02:00
title: AWS EC2 instances
weight: 30
---

#### Compute instances

```HCL
job "aws" "ec2" {
    region = "us-west-1"
    config {
        tag = "env:prod"
        chaos = "terminate"
        count = 8
    }
}
```
chaos config:
* *terminate*: Finds EC2 instances with specified tag and destroys them.
* *reboot*: Finds EC2 instances with specified tag and reboots the instances.
* *stop*: Stops EC2 instances.