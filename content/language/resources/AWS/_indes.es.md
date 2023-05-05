---
date: 2016-04-09T16:50:16+02:00
title: AWS configuración
weight: 05
---
Go-Chaos utiliza el SDK de AWS, por lo que para empezar a ejecutar operaciones de caos en tu infraestructura, se necesitan las credenciales de AWS configuradas.

1. Variables de entorno: `AWS_ACCESS_KEY_ID`, `AWS_SECRET_ACCESS_KEY_ID`, `AWS_SESSION_TOKEN`
2. Archivos de configuración compartida: archivos `.aws/credentials` y `.aws/config`

Si go-chaos se ejecuta dentro de una instancia EC2, deben usarse los roles IAM, por lo que no es necesario configurar las credenciales.

Para la ejecución manual, se recomienda el uso de roles IAM o credenciales compartidas, mientras que para la ejecución automatizada (GitHub Actions, GitLab CI, Jenkins, etc.) se recomienda el uso de roles IAM.