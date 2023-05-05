---
date: 2016-04-09T16:50:16+02:00
title: Notificaciones
weight: 30
---

## Notificaciones


### gmail 

go-chaos puede notificar a una lista de correos electrónicos sobre los cambios ocurridos.

```HCL
notifications "gmail" {
    from = "my-email@gmail.com"
    to = ["manager@gmail.com", "other-manager@gmail.com", "team-mate@gmail.com"]
    body = "Por favor,atentos a cualquier incidente después del experimento en github.com/mi-empresa/chaos/experiment.hcl"
}
```

***Nota:***
Para usar una notificación de Gmail, go-chaos requiere una variable de entorno llamada: **GMAIL_APP_TOKEN**. Para obtener información sobre cómo configurar una contraseña de aplicación en una cuenta de Gmail, consulte la [documentación oficial de Google](https://support.google.com/mail/answer/185833?hl=es). Puede configurar tantas notificaciones de Gmail en el mismo experimento de go-chaos.

### slack

go-chaos puede notificar a una lista de canales de Slack sobre los cambios ocurridos.

```HCL
notifications "slack" {
    to   = ["C04N5HS91MZ", "C04NJH791MU"]
    body = "Experimento de caos en ejecución,atento equipo de desarrollo."
}

```

***Nota:***
Para usar la notificación de Slack, go-chaos requiere una variable de entorno llamada: **SLACK_AUTH_TOKEN**, consulte la documentación oficial de Slack sobre cómo crear una aplicación de Slack y cómo crear un token de aplicación de Slack.

***Nota:***
Requiere IDs de canal en lugar de nombres de canal de Slack, esto cambiará en un futuro cercano.
