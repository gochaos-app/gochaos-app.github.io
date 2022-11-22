---
date: 2016-04-09T16:50:16+02:00
title: AWS Lambda Functions
weight: 40
---

#### Compute Lambda Functions

```HCL
job "aws" "lambda" {
    region = "us-west-2"
     config {
        tag = "tag:example"
        count = 5
        chaos = "stop"
    }
}
```
chaos config:
* *terminate*: Finds lambda functions with specified tag and force deletes them.
* *stop*: Puts reserved concurrency to 0 in found functions. 