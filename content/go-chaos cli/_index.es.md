---
date: 2016-04-09T16:50:16+02:00
title: CLI
pre: "<b>3. </b>"
weight: 30
---

go-chaos es una aplicación de terminal, por lo que necesitarás tener conocimientos básicos de Linux o BSD.

```bash
NAME:
   go-chaos -  Una aplicación basada en terminal que inyecta caos en tu infraestructura en la nube

USAGE:
   go-chaos command [command options]

COMMANDS:
   destroy   Ejecuta destroy con un archivo
   plan      Ejecuta una simulación con un nombre de archivo personalizado
   validate  Valida el experimento
   target    Ejecuta caos en un solo objetivo
   help, h   Muestra una lista de comandos

```

Los comandos básicos son: 

* ***validate***: Lee un archivo y verifica si es legible. Encuentra problemas como valores faltantes en el archivo.
 ```bash
go-chaos validate Experimento.hcl 
```

* ***plan***: Lee un archivo y muestra los recursos donde puede tener lugar las operaciones, este comando no realiza ninguna operación real.

```bash
go-chaos plan Experimento.hcl
```

 * ***destroy***: Lee un archivo, lo valida y comienza a ejecutar las operaciones de caos.
 {{% notice warning %}}
Las acciones detrás de este comando son irreversibles, por favor, úsalo con precaución.
{{% /notice %}}

```bash
go-chaos destroy Experimento.hcl 
```

* ***target***: Lee un archivo y ejecuta un trabajo de objetivo dentro de este archivo.

{{% notice warning %}}
Las acciones detrás de este comando son irreversibles, por favor, úsalo con precaución.
{{% /notice %}}
```bash
  go-chaos target myExperiment.hcl aws.ec2.app1:prod
```

