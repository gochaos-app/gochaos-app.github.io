---
date: 2016-04-09T16:50:16+02:00
title: Features
weight: 40
---

## Control chaos with labels or tags.
This is an important feature, as go-chaos requires a single tag to identify the resources 
to apply the chaos experiment. 

```
  tag = "app:my-super-awesome-app-prod"
```

## Execute within a single region 
Execute a chaos job inside a region, to minimize the blast radius.
```
region = "us-east-1"
```

## Apply chaos to a limited number of resource
Destroys up to the number of resources specified in the count parameter.
```
  config "chaos" {
        count = 5
    }
```

## Different chaos executions
go-chaos does not only destroy resources, it can perform a number of different operations 
in the resources, such as reboot, destroy, stop, delete_content, etc.

This depends on the resource that chaos is being applied. 

## Custom script execution. 
go-chaos can execute custom scripts as part of the same flow and with the all of the parameters in the providers
```
job "script" "python3:script.py" {
    region = "us-west-2"
    namespace = "default"
    project = "project1
    config {
        tag = "hello" 
        chaos = "terminate"    
        count = 3
    }
}
 
```




