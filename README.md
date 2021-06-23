# Building a Secure Cloud Application from scratch

Demo repository for the Israel Clouds talk 2021

## Introduction

This repository includes a sample DevSecOps Github Action workflow that includes secret detection, SAST, DAST and SCA scanners as well as some check against Github API and an integration with Slack in order to get notified about the outcome of each job.

## Sample serverless app

* The sample app for the demo is a serverless application. You can deploy it using Serverless Framework. 
* You can install the Serverless framework CLI using `npm install -g serverless`. 
* To test the application locally, a `docker-compose` file has been added with `localstack`. 
* To deploy the app to localstack use the following command `sls deploy --stage local`.
* In order to get the integration with Slack working, you need to create a Slack app and activate the Incoming Webhooks. Add a webhook on your domain and copy the webhook URL inside the value of a Github secret called `SLACK_WEBHOOK_URL`.

## DevSecOps workflow

The security workflow includes the following security controls:
* Secret Detection using `yelp/detect-secrets`
* SAST using `Bandit`
* DAST using `ZAP`
* SCA using OWASP `dependency-check`
* Github MFA checker
