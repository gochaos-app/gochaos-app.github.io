---
date: 2016-04-09T16:50:16+02:00
title: AWS Setup
weight: 05
---
Go-Chaos uses the AWS SDK, so in order to start executing chaos jobs in your infrastructure
AWS credentials need to be setup. 
1. Environment Variables: `AWS_ACCESS_KEY_ID`, `AWS_SECRET_ACCESS_KEY_ID`, `AWS_SESSION_TOKEN`
2. Shared configuration file: files `.aws/credentials` and `.aws/config`

If Go-Chaos is executed inside an EC2, IAM roles should be used, no need to setup credentials. 

For manual execution, is recommended to use either an IAM role or shared credentials and for
automated execution (GitHub Actions, GitLab CI, Jenkins, etc) is recommended to use IAM roles. 