---
date: 2016-04-09T16:50:16+02:00
title: Usage
chapter: true
pre: "<b>4. </b>"
weight: 40
---
## Usage & Examples 
The following examples and configuration are for guidance on how to create chaos config files and how to execute those, as well as integration with other languages, notifications and .

* [aws](aws) - Simple example on which instances and a lambda function are stopped and sending a slack message with a bash script.
* [kubernetes](k8s) A single file that executes chaos for K8s.
* [GithubActions](https://github.com/gochaos-app/go-chaos-experiments/blob/main/.github/workflows/main_aws.yaml) A workflow file  that setup go-chaos and executes experiments with GitHub actions.

These and more examples can be found at [go-chaos-experiments](https://github.com/gochaos-app/go-chaos-experiments)