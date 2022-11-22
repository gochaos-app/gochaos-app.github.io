---
date: 2016-04-09T16:50:16+02:00
title: Notifications
weight: 30
---

## Resources to apply chaos
go-chaos can notify a list of emails about the changes ocurred. 

```HCL
notifications "gmail" {
    from = "my-email@gmail.com"
    emails = ["manager@gmail.com", "other-manager@gmail.com", "team-mate@gmail.com"]
    body = "Please let's be attentive on any incident after the chaos experiment located in github.com/my-company/chaos/experiment.hcl"
}
```
***Note:***
In order to use a gmail notification, go-chaos requires an environment variable called: **GMAIL_APP_TOKEN**, for how to setup an App Password in a gmail account, please take a look at the [official google documentation](https://support.google.com/mail/answer/185833?hl=en). You can setup as many gmail notifications in the same go-chaos experiment.
