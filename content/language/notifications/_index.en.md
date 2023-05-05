---
date: 2016-04-09T16:50:16+02:00
title: Notifications
weight: 30
---

## Notifications structure


### gmail 

go-chaos can notify a list of emails about the changes ocurred. 

```HCL
notifications "gmail" {
    from = "my-email@gmail.com"
    to = ["manager@gmail.com", "other-manager@gmail.com", "team-mate@gmail.com"]
    body = "Please let's be attentive on any incident after the chaos experiment located in github.com/my-company/chaos/experiment.hcl"
}
```

***Note:***
In order to use a gmail notification, go-chaos requires an environment variable called: **GMAIL_APP_TOKEN**, for how to setup an App Password in a gmail account, please take a look at the [official google documentation](https://support.google.com/mail/answer/185833?hl=en). You can setup as many gmail notifications in the same go-chaos experiment.


### slack

go-chaos can notify a list of slack channels about the changes ocurred. 

```HCL
notifications "slack" {
    to   = ["C04N5HS91MZ", "C04NJH791MU"]
    body = "chaos experiment running, to check dev teams and get latency in qa"
}
```

***Note:***
In order to use the slack notification, go-chaos requires an environment variable called: **SLACK_AUTH_TOKEN**, please refer to the official slack documentation on how to create an Slack App and the creation of a Slack App Token.

***Note:***
Requires channelIDs instead of slack channel names, this will change in the near future. 
