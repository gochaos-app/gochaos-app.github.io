---
date: 2016-04-09T16:50:16+02:00
title: CLI
pre: "<b>3. </b>"
weight: 30
---

go-chaos is a terminal app, so you will need to have basic knowledge on Linux or BSD. 

```bash
NAME:
   go-chaos - A terminal based app that injects chaos into your cloud infrastructure

USAGE:
   go-chaos command [command options]

COMMANDS:
   destroy   Execute destroy with custom file name
   plan      Execute a dry run with custom file name
   validate  Validate chaos file
   target    Execute chaos on a single target
   help, h   Shows a list of commands or help for one command

```

Basic commands are:
 * ***validate***: reads a file and checks if the file is readeable. Finds issues such as missing values for parameters. 
 ```bash
go-chaos validate myExperiment.hcl 
```

* ***plan*** reads a file and outputs the resources where the chaos operation may take place, this command doesn't actually perform any operation.
```bash
go-chaos plan myExperiment.hcl
```
 * ***destroy***: reads a file, validates it and starts to executing chaos job operations, and a script if it is present.
 {{% notice warning %}}
 The actions behind this command are irreversible, please use with caution
{{% /notice %}}
```bash
go-chaos destroy myExperiment.hcl 
```
* ***target***: reads a file and executes a target job inside this file, eg, 
{{% notice warning %}}
 The actions behind this command are irreversible, please use with caution
{{% /notice %}}
```bash
 go-chaos target myExperiment.hcl aws.ec2.app1:prod
```

* ***server***: reads a server configuration toml file, start a server and can execute chaos experiments from a remote location.
{{% notice warning %}}
Server functionality is still in beta, use with caution
{{% /notice %}}
