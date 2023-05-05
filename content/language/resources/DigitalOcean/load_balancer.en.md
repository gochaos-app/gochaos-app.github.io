---
date: 2016-04-09T16:50:16+02:00
title: DigitalOcean Load Balancer
weight: 100
---

#### Load Balancer

```HCL
job "do" "load_balancer" {
    config {
        tag = "app"
        chaos = "removeDroplets"
        count = 1
    }
}
```
chaos config:
* *removeDroplets*: Finds a load balancer with tag and removes droplets from it.
* *removeRules*: Finds a load balancer with tag and removes rules from it.
