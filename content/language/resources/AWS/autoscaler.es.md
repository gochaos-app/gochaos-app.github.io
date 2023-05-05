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
* *terminate*: Encuentra grupos de autoescalamiento con la etiqueta correspondiente y los destruye.
* *update*: Encuentra un solo grupo con la etiqueta y configura los parámetros maximo y deseado al numero en el parámetro count, al miemso tiempo el minímo lo configura a 0.
* *desired*: Sets the desired capacity, not modifying the other states (minimum and maximum). The desired capacity has to be equal or below the maximum capacity with this chaos action.

