---
description: What is needed to run dragondrop in your cloud?
---

# Requirements

## Terraform Modules

For supported public clouds, we provide open-sourced [Terraform Modules](https://registry.terraform.io/namespaces/dragondrop-cloud) which provision the requisite infrastructure needed to receive https requests that trigger the dragondrop.cloud container hosted on serverless compute.

This let's you get up and running in your cloud as quickly as you can run `terraform apply`!

## Overall Architecture

1\) Provide serverless compute that can run a container (in this case it will be running dragondrop's publicly accessible container).

2\) Provide an https endpoint to which dragondrop can send requests for invoking the container.

**Note**: While it is possible to build your own infrastructure from scratch to host dragondrop, we advise against it and are not able to provide customer service related to infrastructure-hosting challenges when our modules are not being employed.
