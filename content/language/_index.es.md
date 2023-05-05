---
date: 2016-04-09T16:50:16+02:00
title: Lenguaje de configuración
pre: "<b>2. </b>"
weight: 20
---
go-chaos usa HCL como lenguaje de configuración. 

### ¿Por qué se eligió HCL?

* A diferencia de otros formatos, HCL es fácilmente legible tanto por máquinas como por personas
* No tiene problemas con la indentación como lo tiene YAML.
* Puede ser leido por otros lenguajes.

### Configuración simple

```HCL
app = "my awesome prod app"
description = "Esta aplicación se ejecuta en EC2, el experimento consiste en terminar 5 instancias en la región us-east-1" 
    
job "aws" "ec2" {
    region = "us-east-1"
    config "chaos" {
        tag = "Name:app-prod"
        chaos = "terminate"
        count = 5
    }
}
```

go-chaos buscará instancias EC2 en la región *us-east-1* con la etiqueta`Name:app-prod`, aleatoriamente seleccionará `5` y las va a terminar.







