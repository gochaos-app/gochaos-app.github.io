---
title: "Go-Chaos"
chapter: false
weight: 5

---
# Go-Chaos
Go-Chaos es una aplicación de línea de comandos (cli) para hacer que la ingeniería del caos sea simple mediante experimentos como código.


## Características principales

* Lee experimentos de ingeniería del caos en formato HCL.
* Limita el alcance del impacto con la ayuda de etiquetas.
* Modelos de perturbación tanto de eliminación de datos como de apagado de servidores.

## Supported Services
Go-Chaos admite la experimentación en los siguientes proveedores:

* AWS
* GCP
* DigitalOcean
* Kubernetes


## Go-Chaos workflow

- escribir
- validar
- planificar
- destruir

Comienza creando un directorio:
```bash
mkdir chaosExperiment && cd chaosExperiment
```
Crea un archivo de configuración y nombralo `experiment.hcl`

```hcl
app = "ProdApp"
description = "experimento de ingenería de caos" 

job "aws" "ec2" {
    region = "us-east-1"
    config {
        tag = "Name:prod-web-server"
        chaos = "terminate"
        count = 6
    }
}
```

Ejecuta el experimento:
```bash
go-chaos destroy experiment.hcl
```
Este último experimento terminará 6 instancias de EC2 con la etiqueta Name:prod-web-server en la región us-east-1.




## Contribuir
***Go-Chaos*** está escrito en Go, se están desarrollando más características (y correcciones de errores), si quieres una característica o contribuir con código, por favor haz un ***[Pull Request](https://github.com/gochaos-app/go-chaos)***..



{{% button href="https://github.com/gochaos-app/go-chaos-experiments" %}}go-chaos experimentos{{% /button %}}

{{% button href="https://github.com/gochaos-app/gochaos-app.github.io" %}}Documentación{{% /button %}}