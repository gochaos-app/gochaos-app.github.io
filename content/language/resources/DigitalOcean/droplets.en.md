---
date: 2016-04-09T16:50:16+02:00
title: DigitalOcean Droplets
weight: 90
---

#### Compute Droplets

```HCL
job "do" "droplet" {
    config {
        tag = "env:prod"
        chaos = "terminate"
        count = 1
    }
}
```
chaos config:
* *terminate*: Finds droplets with specified tag and destroys them.
* *reboot*: Finds droplets with specified tag and reboots the instances.
* *stop*: Tries to shutdown gracefully the found droplets.
* *poweroff*: PowerOffs found droplets with tag.