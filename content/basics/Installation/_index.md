---
date: 2016-04-09T16:50:16+02:00
title: Installation
weight: 30
---

go-chaos is really simple to install, simply download the binary and place it in the path on your system. 

[Latest release](https://github.com/gochaos-app/go-chaos/releases/tag/v0.2.0)


Download the compatible binary. Current executable files built are for the

{{< tabs groupID="Download">}}
{{% tab name="Linux" %}}
  
  [Linux x64](https://github.com/gochaos-app/go-chaos/releases/download/v0.2.0/go-chaos-linux-amd64) 
  
  [Linux arm64](https://github.com/gochaos-app/go-chaos/releases/download/v0.2.0/go-chaos-linux-arm64) 

{{% /tab %}}
{{% tab name="FreeBSD" %}}
  [FreeBSD x64](https://github.com/gochaos-app/go-chaos/releases/download/v0.2.0/go-chaos-freebsd-amd64)
{{% /tab %}}
{{% tab name="MacOS" %}}
  [macos x64](https://github.com/gochaos-app/go-chaos/releases/download/v0.2.0/go-chaos-darwin-amd64) 
  
  [macos m1](https://github.com/gochaos-app/go-chaos/releases/download/v0.2.0/go-chaos-darwin-m1)
{{% /tab %}}
{{< /tabs >}}


All architectures have versions for both *amd64*  and *arm64*

Compile from source:

```
git clone https://github.com/gochaos-app/go-chaos.git
cd go-chaos
make install
```home
This will create a binary for your system and place it inside ${HOME}/bin please make sure that this directory exists and
is on  the systems PATH.


If the previous option is not available on your system, use:
```
make prod
```
to compile the code, once compiled, install by copying the binary to your executables location path

```
cp go-chaos /usr/local/bin/go-chaos
```
