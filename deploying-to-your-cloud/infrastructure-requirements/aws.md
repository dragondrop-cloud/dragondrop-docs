---
description: >-
  Learn about our recommended infrastructure set up within your AWS cloud
  environment.
---

# AWS

<figure><img src="../../.gitbook/assets/2023-03-05 AWS Infrastructure Module.png" alt=""><figcaption><p>Our Terraform module for AWS infrastructure will get you spun up with a secure, serverless hosting of dragondrop in minutes.</p></figcaption></figure>

## Terraform Module

We strongly recommend using our [Terraform Module](https://registry.terraform.io/modules/dragondrop-cloud/dragondrop-compute/aws/latest) to host dragondrop within your AWS environment.

It creates all of infrastructure illustrated in the above diagram, with locked-down permissions on each piece of compute, outputting an HTTPS request to which our web application can send requests to trigger your Job. All you need to do is fill in environment variables on the needed for the ECS Fargate Task, and then cloud infrastructure for that Job is complete!

Using our Terraform module, we estimate that Jobs can be **deployed within your cloud environment from scratch in less than 30 minutes of developer time**.

### Building Your Own Hosting Infrastructure in AWS

We do not provide customer service for infrastructure hosting dragondrop created outside of our modules, and so strongly recommend using our [Terraform Module](https://registry.terraform.io/modules/dragondrop-cloud/dragondrop-compute/aws/latest) to provision the infrastructure needed. That being said, Amazon Web Services (AWS) makes it possible for you to provide serverless compute to dragondrop's container if you want to build your own set up.&#x20;

Our recommended approach:

1\) Define a ECS Fargate task that hosts the proprietary dragondrop container.

2\) Define an HTTPS endpoint that triggers the ECS Fargate task, likely using a Lambda function.

3\) Provide the API endpoint to your dragondrop [job definition](../../getting-started/jobs/creating-a-job.md). Done!
