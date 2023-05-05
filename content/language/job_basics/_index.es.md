---
date: 2016-04-09T16:50:16+02:00
title: Uso
weight: 10
---

## Controlar el experimento. 

go-chaos tiene diferentes parámetros para controlar los experimentos de caos que se ejecutan en la infraestructura.

## Scripts config.
```
script {
    executor   = "bash"
    source     = "destroy.sh"
}
```
Solo se permite un script por archivos de configuración, y el script se ejecutará al final después de que todos los jobs hayan finalizado.

* executor: binario o comando que ejecutará el script. El sistema tiene que tener instalado este binario 
* source: Nombre del script a ejecutar.

## Job config.

* region:    Enceuntra recursos en una región especifíca, solo para proveedores de la nubes, como aws, gcp (Opcional). 
* project:   Encuentra recursos en un proyecto, exclusiva a gcp.
* namespace: Detectar recursos como pods y deployments en un namespace, exclusivo a kubernetes (Optional). 

### Chaos config.
* tag: etiqueta para encontrar los recursos (ambos k8s, y provedorees de nube). 
* chaos: Parámetro que realiza una acción específica en los recursos encontrados, dependende del tipo de recurso.
* count: Número entero que define el número de recursos en los cuales aplicar el parámetro de caos mencionado anteriormente.
