---
date: 2016-04-09T16:50:16+02:00
title: K8s
---

## Situación

En el siguiente entorno, tenemos una aplicación de inventario que se ejecuta en k8s, la hipótesis es que nuestros clientes puedan obtener productos sin problema incluso si nuestra aplicación se escala hacia abajo o hacia arriba.


## Experimento

Cree un nuevo archivo de experimento de caos llamado inventory-config.hcl.


```HCL
app = "inventory app"
description = "Experimento de caos para la aplicación de inventario, verificar si los clientes pueden agregar productos en el carrito"
 

job "kubernetes" "pod" {
    namespace = "inventory-app"
    config {
        tag = "app:inventory-prod"  
        chaos = "terminate"         
        count = 5                   
    }
}
```
El trabajo anterior buscará 5 pods con la etiqueta app:inventory-prod y los eliminará.

En el mismo experimento, verificamos cómo se comporta el clúster con cambios tan rápidos.


```HCL
job "kubernetes" "deployment" {
    namespace = "inventory-app"
    config {
        tag = "app:inventory-prod" 
        chaos = "update"
        count = 20
    }
}
```
Este trabajo aumentará a 20 el número de pods del deployment con la etiqueta app:inventory-prod.
