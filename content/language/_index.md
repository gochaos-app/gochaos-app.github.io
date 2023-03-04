---
date: 2016-04-09T16:50:16+02:00
title: Configuration language
pre: "<b>2. </b>"
weight: 20
---
go-chaos uses HCL for the configuration language. 

### Why HCL was chosen 

* Unlike other formats, HCL is easily readable by machines and people. 
* It doesn't have such problems with indenting like yaml does. 
* It can be parsed by several languages.

### Simple config

```HCL
app = "my awesome prod app"
description = "This app runs over EC2, experiment consists on terminate 5 instances in us-east-1 region" 
    
job "aws" "ec2" {
    region = "us-east-1"
    config "chaos" {
        tag = "Name:app-prod"
        chaos = "terminate"
        count = 5
    }
}
```

go-chaos will look for EC2 instances in the region *us-east-1* with the tag `Name:app-prod`, randomly select `5` and `terminate` those them.  







