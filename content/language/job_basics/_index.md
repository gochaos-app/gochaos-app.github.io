---
date: 2016-04-09T16:50:16+02:00
title: Usage
weight: 10
---

## How to control the experiment. 

go-chaos has different parameters to control the chaos experiments executed in the infrastructure. 

## Scripts config.
```
script {
    executor   = "bash"
    source     = "destroy.sh"
}
```
Only one script is permitted for chaos config file, and the script will always be executed after all jobs have finished

* executor: executable file which will execute the script. As long as the local system has the binary 
it can run any script. 
* source: name of the script, it has to be located in the directory where go-chaos is run.

## Job config.

* region:    Find resources in specific region, exclusive to cloud providers such as aws, gcp (Optional). 
* project:   Find resources in specific project, exclusive to gcp.
* namespace: Find resources such as pods and deployments in specific namespace, exclusive to kubernetes provider (Optional). 

### Chaos config.
* tag: Single tag to find resources (for both k8s and cloud providers). 
* chaos: Parameter that performs a specific action on resources found, depends on resource. 
* count: Integer that defines the number of resources to apply the chaos paramenter mentioned above. 
