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

## Different chaos executions
go-chaos does not only destroy resources, it can perform a number of different operations 
in the resources, such as reboot, destroy, stop, delete_content, etc.

This depends on the resource that chaos is being applied. 

## Custom script execution at the end of the chaos experiment. 
go-chaos can execute a script at the end of the experiment, this lets you create 
custom alerts, execute custom steps after the chaos experiment, or simple make an
announcement that a chaos engineering experiment took place.

## Develop your own custom modules (pre-release feature)
go-chaos can accept modules and executes those as part of the chaos jobs in the file. The modules 
should contain the following code: 

```
package main

import (
  ...
)


func ChaosFunc(region string, service string, project string, namespace string, tag string, chaos string, number int) {
  ...
}
```

This function is the entrypoint of the module, needs to have those arguments which correspond to the structure of the job chaos. 
You can use these arguments with any purpose according to the custom specification.


