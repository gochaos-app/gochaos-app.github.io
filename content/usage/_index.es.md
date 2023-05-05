---
date: 2016-04-09T16:50:16+02:00
title: Usage
chapter: true
pre: "<b>4. </b>"
weight: 40
---
## Ejemplos
Los siguientes ejemplos y configuraciones sirven como guía para crear archivos de configuración de caos y cómo ejecutarlos, así como para integrar con otros lenguajes, notificaciones, etc.

* [aws](aws) -  Un ejemplo sencillo en el que se detienen instancias y una función lambda en AWS y se envía un mensaje de Slack con un script de bash.
* [kubernetes](k8s) Un archivo único que ejecuta el caos en Kubernetes.
* [GithubActions](https://github.com/gochaos-app/go-chaos-experiments/blob/main/.github/workflows/main_aws.yaml) Un archivo de GitHub Actions que configura go-chaos y ejecuta experimentos.


Estos y más ejemplos se pueden encontrar en [go-chaos-experiments](https://github.com/gochaos-app/go-chaos-experiments)