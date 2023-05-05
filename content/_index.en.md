---
title: "Go-Chaos"
chapter: false
weight: 5

---
# Go-Chaos
Go-Chaos is a cli app to make chaos engineering simple with experiments as code. 

## Main Features
* Reads chaos engineering experiments in HCL format. 
* Limit blast radius with the help of tags.
* Both data deletion and server-shutdown perturbation models. 

## Supported Services
Go-chaos support the experimentation on the following providers:
* AWS
* GCP
* DigitalOcean
* Kubernetes
* custom modules (pre-release feature)

## Go-Chaos workflow

- write
- validate
- plan
- destroy

Start by creating a directory
```bash
mkdir chaosExperiment && cd chaosExperiment
```
Create a simple chaos config file and name it `experiment.hcl`

```hcl
app = "ProdApp"
description = "this is a chaos engineering experiment" 

job "aws" "ec2" {
    region = "us-east-1"
    config {
        tag = "Name:prod-web-server"
        chaos = "terminate"
        count = 6
    }
}
```

Execute the experiment:
```bash
go-chaos destroy experiment.hcl
```

This last experiment will terminate 6 EC2 instances with the tag *Name:prod-web-server* in region *us-east-1*

## Contribute

***Go-Chaos*** is written in Go, more features (and bugfixes) are in development, if you want a feature or contribute with code, please make a ***[Pull Request](https://github.com/gochaos-app/go-chaos)***.


{{% button href="https://github.com/gochaos-app/go-chaos-experiments" %}}go-chaos experiments{{% /button %}}

{{% button href="https://github.com/gochaos-app/gochaos-app.github.io" %}}This documentation{{% /button %}}