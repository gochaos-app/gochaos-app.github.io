---
date: 2016-04-09T16:50:16+02:00
title: Usage
weight: 10
---

## How to control the experiment. 

go-chaos has different parameters to control the chaos experiments executed in the infrastructure. 

## Job config.

* region:    Find resources in specific region, exclusive to cloud providers such as aws, gcp (Optional). 
* project:   Find resources in specific project, exclusive to gcp.
* namespace: Find resources such as pods and deployments in specific namespace, exclusive to kubernetes provider (Optional). 

### Chaos config.
* tag: Single tag to find resources (for both k8s and cloud providers). 
* chaos: Parameter that performs a specific action on resources found, depends on resource. 
* count: Integer that defines the number of resources to apply the chaos parameter mentioned above. 

## Script config. 
The same parameters can be passed to scripts as part. 
```
job "script" "python3:script.py" {
    region = "us-west-2"
    namespace = "default"
    project = "project1
    config {
        tag = "myapp" 
        chaos = "terminate"    
        count = 3
    }
}
```
In this example a `python3` script called `script.py` will be executed by go-chaos, the parameters are available as environment variablers in the session. The executable `python3` needs to be available in system `$PATH`. 

```
{
    "REGION" : region,
    "PROJECT" : project,
    "NAMESPACE" : namespace, 
    "TAG" : tag,
    "CHAOS" : chaos,
    "NUMBER": number
}

```
