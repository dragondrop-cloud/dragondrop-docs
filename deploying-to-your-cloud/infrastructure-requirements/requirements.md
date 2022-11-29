---
description: What is needed to run dragondrop in your cloud?
---

# Requirements

## Overall Architecture

1\) Provide serverless compute that can run a container (in this case it will be running dragondrop's publicly accessible container).

2\) Provide an https endpoint to which dragondrop can send requests for invoking the container.

## Terraform Modules

For supported public clouds, we provide open-sourced Terraform Modules which provision the requisite infrastructure needed to receive https requests which trigger the dragondrop.cloud container hosted on serverless compute.

This let's you get up and running in your cloud as quickly as you can run `terraform apply!`
