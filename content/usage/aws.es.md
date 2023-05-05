---
date: 2016-04-09T16:50:16+02:00
title: AWS 
---

## Situación
En esta situación teórica, se tiene el servicio de inicio de sesión (Login) ejecutándose dentro de instancias AWS EC2. Se llama a una función lambda para obtener la resolución del dispositivo, en la cual se aplicará caos también.

## Experimento

Start by creating a new chaos experiment file called `config.hcl` 
copy-paste the following code:
```HCL

app = "Login"
description = "Experimento de caos para la aplicación de inicio de sesión"

job "aws" "ec2" {
    region = "us-east-1"
    config {
        tag = "Name:login-app-prod" 
        chaos = "stop"              
        count = 3                   
    }
}
```

go-chaos buscará 3 instancias de AWS en la región us-east-1 con la etiqueta Name:login-app-prod. La acción de caos requerida es detener (stop) las instancias.

En el mismo archivo agregamos otro trabajo:

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
Este trabajo establecerá la concurrencia en 0 de una sola función lambda con la etiqueta Name:resolution-scale-prod.

El experimento de caos puede tener una única ejecución de script al final de la ejecución de los trabajos, en este caso se utiliza un script para enviar un mensaje de Slack. Cree un nuevo archivo y llámelo notification.sh, y colóquelo en el mismo directorio que el archivo de experimento de caos.

```bash
curl -X POST -H 'Content-type: application/json' --data '{"text":"running chaos experiment, please be attentive!"}' <WEBHOOK>
```
El archivo final debería verse así:

```HCL
app = "Login"
description = "Experimento de caos para la aplicación de inicio de sesión"

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