---
date: 2016-04-09T16:50:16+02:00
title: Server configuration 
pre: "<b>5. </b>"
weight: 50
---
{{% notice warning %}}
Function still in development, use with caution
{{% /notice %}}

## go-chaos server configuration
go-chaos can act as a server, it reads the config file and it executes chaos experiments remotely.

## Start server.
This is an important feature, as go-chaos requires a single tag to identify the resources 
to apply the chaos experiment. 

```hcl
  go-chaos s server.toml
```

## Server configuration file
The server configuration file is a toml key value format. A simple config file will look like this:

```toml
port = "3333" 
remote = "git@github.com:gochaos-app/go-chaos-experiments.git" 
branch = "refs/heads/main" 
path = "/tmp/test" 
```

* port, optional parameter, default is 3333
* remote, git repository that contains go-chaos experiments for different environments or applications.
* branch, default main, 
* path, system path where repository will be located, `/tmp` recommended

To execute a chaos experiment:
curl http://go-chaos-url:3333/experiment?config=path_to_chaos_experiment.hcl

## Example

It is recommended that the chaos experiments are versioned in a git repository. 

Git repository structure:
```
git project
|   README.md
|   server.toml
|___inventory
|   |___README.md
|   |___inventory_prod.hcl
|   |___inventory_qa.hcl
|___customer-experience
    |___README.md
    |___customer_experience_prod.hcl
    |___customer_experience_qa.hcl
    |___customer_experience_dev.hcl
```
* server config file
```toml
port = "1234"
remote = "git@github.com:myorg/go-chaos-experiments.git"
branch = "refs/heads/main"
path = "/tmp/chaos"
```

Execute go-chaos server
```
go-chaos s server.toml
```

This last command will start the server in port **1234**, it clones the **go-chaos-experiment** repository from github in the **/tmp/chaos** path.

To execute a single go-chaos experiment:
```
curl localhost:1234/experiment?config=inventory/inventory_prod.hcl
```

this last curl command is equivalent to:
```
go-chaos d inventory/inventory_prod.hcl
```

{{% notice warning %}}
Be really careful on which chaos experiments get executed, actions cannot be undone - go-chaos server is still in development.
{{% /notice %}}
