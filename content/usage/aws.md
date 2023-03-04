---
date: 2016-04-09T16:50:16+02:00
title: AWS 
---

## Environment
In this theoretical environment, the team has the Login service running inside AWS EC2 instances. 
A lambda function gets called to obtain the device resolution, will apply chaos on that as well.

## Experiment

Start by creating a new chaos experiment file called `config.hcl` 
copy-paste the following code:
```HCL

app = "Login"
description = "Chaos Experiment for login app" 

job "aws" "ec2" {
    region = "us-east-1"
    config {
        tag = "Name:login-app-prod" 
        chaos = "stop"              
        count = 3                   
    }
}
```

Go-chaos will search for *3* aws instances in *us-east-1* region with the tag *Name:login-app-prod*. Required chaos action is to *stop* the instances 

In the same file we add another job

```HCL
job "aws" "lambda" {
    region = "us-east-1"
    config {
        tag = "Name:resolution-scale-prod" 
        chaos = "stop"              
        count = 1                   
    }
}
```
This job will put concurrency=0 to a single lambda with tag Name:resolution-scale-prod

The chaos experiment, can have a single script execution at the end of the jobs execution, in this case a script is used to send a slack message. Create a new file, name it *notification.sh*, and place it under the same directory as the chaos experiment file. 

```bash
curl -X POST -H 'Content-type: application/json' --data '{"text":"running chaos experiment, please be attentive!"}' <WEBHOOK>
```
Final file should look like this:

```HCL
app = "Login"
description = "Chaos Experiment for login app" 

job "aws" "ec2" {
    region = "us-east-1"
    config {
        tag = "Name:login-app-prod" 
        chaos = "stop"              
        count = 3                   
    }
}

job "aws" "lambda" {
    region = "us-east-1"
    config {
        tag = "Name:resolution-scale-prod" 
        chaos = "stop"              
        count = 1                   
    }
}

script {
    executor    = "bash"
    source      = "notification.sh" 
}
```