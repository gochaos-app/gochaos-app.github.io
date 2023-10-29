---
date: 2016-04-09T16:50:16+02:00
title: Instalación
weight: 30
---

go-chaos es muy fácil de instalar, simplemente descarga el binario y colócalo en la ruta de tu sistema.


[Ultima Versión](https://github.com/gochaos-app/go-chaos/releases/tag/v0.6.0)


Descarga el binario compatible. Los archivos ejecutables se construyen para las siguientes arquitecturas:

{{< tabs groupID="Download">}}
{{% tab name="Linux" %}}
  
  [Linux x64](https://github.com/gochaos-app/go-chaos/releases/download/v0.6.0/go-chaos-linux-amd64) 
  
  [Linux arm64](https://github.com/gochaos-app/go-chaos/releases/download/v0.6.0/go-chaos-linux-arm64) 

{{% /tab %}}
{{% tab name="FreeBSD" %}}
  [FreeBSD x64](https://github.com/gochaos-app/go-chaos/releases/download/v0.6.0/go-chaos-freebsd-amd64)
{{% /tab %}}
{{% tab name="MacOS" %}}
  [macos x64](https://github.com/gochaos-app/go-chaos/releases/download/v0.6.0/go-chaos-darwin-amd64) 
  
  [macos m1](https://github.com/gochaos-app/go-chaos/releases/download/v0.6.0/go-chaos-darwin-m1)
{{% /tab %}}
{{< /tabs >}}

Todas las arquitecturas tienen versiones tanto para amd64 como para arm64.

Compila desde el código fuente:

```
git clone https://github.com/gochaos-app/go-chaos.git
cd go-chaos
make install
```
Esto creará un binario para tu sistema y lo colocará dentro de ${HOME}/bin, por favor asegúrate de que este directorio exista y se encuentre en la ruta del sistema.


Si la opción anterior no está disponible en tu sistema, usa:

```
make prod
```

para compilar el código. Una vez compilado, instálalo copiando el binario a la ruta de ubicación de tus ejecutables:

```
cp go-chaos /usr/local/bin/go-chaos

```
