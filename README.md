# sample-knative-composition
Sample composition of serverless event-drive analytics application using Knative


## Overview

This sample demonstrates how to compose anltics for 
events coming from simple loan workflow. The workflow had four
activities:
* Receive
* Evaluate
* Gather (optional activity to investigate loan)
* Decide

## Reqirements

Knative Serving and Eventing version 1.13.
For instrucitons to install see for example [Red Hat Knative Tutorial](https://redhat-developer-demos.github.io/knative-tutorial/knative-tutorial/index.html)


## Deployment steps

See [README in config directory](config/README.md).

## TODO

Elastic Search and Kibana Open Distor version with link to docker-compose and/or k8s install

Use sample functions and events from [tutorial](https://github.com/aslom/serverless-nyc-bai-case-study)
