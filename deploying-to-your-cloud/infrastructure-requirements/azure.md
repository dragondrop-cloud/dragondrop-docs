---
description: >-
  Learn about our recommended infrastructure set up within your Azure cloud
  environment.
---

# Azure

<figure><img src="../../.gitbook/assets/2023-06-14-azure-module (1).png" alt=""><figcaption><p>Our Terraform module for AWS infrastructure will get you spun up with a secure, serverless hosting of dragondrop in minutes.</p></figcaption></figure>

## Terraform Module

We strongly recommend using our [Terraform Module](https://registry.terraform.io/modules/dragondrop-cloud/dragondrop-compute/azurerm/latest) to host dragondrop within your Azure environment.

It creates all of infrastructure illustrated in the above diagram, with locked-down permissions on each piece of compute, outputting an HTTPS request to which our web application can send requests to trigger your Job. All you need to do is fill in environment variables on the Azure Container App, and then cloud infrastructure for that Job is complete!

Using our Terraform module, we estimate that Jobs can be **deployed within your cloud environment from scratch in less than 30 minutes of developer time**.

### Building Your Own Hosting Infrastructure in Azure

We do not provide customer service for infrastructure hosting dragondrop created outside of our modules, and so strongly recommend using our [Terraform Module](https://registry.terraform.io/modules/dragondrop-cloud/dragondrop-compute/aws/latest) to provision the infrastructure needed. That being said, Azure makes it possible for you to provide serverless compute to dragondrop's container if you want to build your own set up.&#x20;

Our recommended approach:

1\) Define an Azure container instance that hosts the dragondrop container.

2\) Define an HTTPS endpoint that triggers the Azure Container Instance or Azure Container App Job, likely using an Azure Container App or an Azure Function.

3\) Provide the API endpoint to your dragondrop [job definition](../../getting-started/jobs/creating-a-job.md). Done!
