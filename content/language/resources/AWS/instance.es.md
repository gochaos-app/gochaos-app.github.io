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
* *terminate*: Encuentra instancias EC2 y las destruye.
* *reboot*: Reinicia instancias EC2.
* *stop*: Para instancias EC2.