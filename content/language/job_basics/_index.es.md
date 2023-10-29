---
date: 2016-04-09T16:50:16+02:00
title: Uso
weight: 10
---

## Controlar el experimento. 

go-chaos tiene diferentes parámetros para controlar los experimentos de caos que se ejecutan en la infraestructura.

## Job config.

* region:    Enceuntra recursos en una región especifíca, solo para proveedores de la nubes, como aws, gcp (Opcional). 
* project:   Encuentra recursos en un proyecto, exclusiva a gcp.
* namespace: Detectar recursos como pods y deployments en un namespace, exclusivo a kubernetes (Optional). 

### Chaos config.
* tag: etiqueta para encontrar los recursos (ambos k8s, y provedorees de nube). 
* chaos: Parámetro que realiza una acción específica en los recursos encontrados, dependende del tipo de recurso.
* count: Número entero que define el número de recursos en los cuales aplicar el parámetro de caos mencionado anteriormente.

## Configuration Script

Los mismos parametros se pueden pasar a un script personalizados 
```
job "script" "python3:script.py" {
    region = "us-west-2"
    namespace = "default"
    project = "project1
    config {
        tag = "myapp" 
        chaos = "terminate"    
        count = 3
    }
}
```
En el ejemplo el script `script.py` es ejecutado con `python3`. Los parametros estan disponibles como variables de ambiente durante la sesion. El ejecutable necesita `python3` debe estar disponible en el `$PATH` del sistema

```
{
    "REGION" : region,
    "PROJECT" : project,
    "NAMESPACE" : namespace, 
    "TAG" : tag,
    "CHAOS" : chaos,
    "NUMBER": number
}

```
