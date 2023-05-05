---
date: 2016-04-09T16:50:16+02:00
title: Características
weight: 40
---

## Controla el caos con etiquetas.
Esta es una característica importante, ya que go-chaos requiere una sola etiqueta para identificar los recursos en los que se aplicará el experimento de caos.

```
  tag = "app:my-super-aplicación-prod"
```

## Ejecución en una única región.
Ejecuta un trabajo de caos dentro de una región para minimizar el radio de acción.
```
region = "us-east-1"
```

## Aplicar el caos a un número limitado de recursos.
Destruye el número de recursos especificados con el parámetro "count".


## Ejecuciones de caos diferentes.
go-chaos no solo destruye recursos, sino que puede realizar una serie de operaciones diferentes en los recursos, como reiniciar, destruir, detener, eliminar contenido, etc.

Esto depende del recurso al que se esté aplicando el caos.

## Ejecución de scripts al final del experimento.
go-chaos puede ejecutar un script al final del experimento, lo que le permite crear alertas personalizadas, ejecutar pasos personalizados después del experimento de caos o simplemente notificar de que se ha realizado un experimento de ingeniería de caos.


