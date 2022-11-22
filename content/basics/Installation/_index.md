---
date: 2016-04-09T16:50:16+02:00
title: Installation
weight: 30
---

go-chaos is really simple to install, simply download the binary and place it in the path on your system. 

[Latest release](https://github.com/gochaos-app/go-chaos/releases/tag/v0.0.0)


Download the compatible binary. Current executable files built are for the

{{< tabs groupID="Download">}}
{{% tab name="Linux" %}}
  
  [Linux x64](https://github.com/gochaos-app/go-chaos/releases/download/v0.0.0/go-chaos-linux-amd64) 
  
  [Linux arm64](https://github.com/gochaos-app/go-chaos/releases/download/v0.0.0/go-chaos-linux-arm64) 

{{% /tab %}}
{{% tab name="FreeBSD" %}}
  [FreeBSD x64](https://github.com/gochaos-app/go-chaos/releases/download/v0.0.0/go-chaos-freebsd-amd64)
{{% /tab %}}
{{% tab name="MacOS" %}}
  [macos x64](https://github.com/gochaos-app/go-chaos/releases/download/v0.0.0/go-chaos-darwin-amd64) 
  
  [macos m1](https://github.com/gochaos-app/go-chaos/releases/download/v0.0.0/go-chaos-darwin-m1)
{{% /tab %}}
{{< /tabs >}}


 
 

All arquitectures have versions for both *amd64*  and *arm64*

Compile from source:

```
git clone https://github.com/gochaos-app/go-chaos.git
cd go-chaos
make prod
```
This will create a binary for your system. 

Once downloaded or compiled, install by copying the binary to your executables location path

```
cp go-chaos /home/${USER}/bin/go-chaos

```
