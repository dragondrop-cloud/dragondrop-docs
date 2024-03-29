---
description: >-
  Learn about our recommended infrastructure set up for deployments to Google
  Cloud Platform (GCP).
---

# GCP

<figure><img src="../../.gitbook/assets/2023-01-18 GCP Module Infrastructure.png" alt=""><figcaption><p>Our Terraform module for GCP infrastructure will get you spun up with a secure, serverless hosting of dragondrop in minutes. </p></figcaption></figure>

## Terraform Module

We strongly recommend using our [Terraform Module](https://registry.terraform.io/modules/dragondrop-cloud/dragondrop-compute/google/latest) to host dragondrop within your cloud.

It creates a Cloud Run Service instance with a new service principal that can only update and invoke Cloud Run Jobs. Further, it provisions the needed Cloud Run Job, complete with all needed environment variable keys (you need to still add the values to Google Secret Manager). The Cloud Run Service instance uses our open-sourced [Flask API service](https://github.com/dragondrop-cloud/cloud-run-job-http-trigger) container, whereas the Cloud Run Job uses our proprietary dragondrop.cloud container. All you need to do is fill in the environment variables needed for the Cloud Run Job, and then cloud infrastructure for that Job is complete!

Using our Terraform module, we estimate that most Jobs can be **deployed within your cloud environment from scratch in less than 30 minutes of developer time**.

### Building Your Own Hosting Infrastructure in GCP

We do not provide customer service for infrastructure hosting dragondrop created outside of our modules, and so strongly recommend using our [Terraform Module](gcp.md#terraform-module) to provision the infrastructure needed. That being said, Google Cloud Platform (GCP) makes it possible for you to provide serverless compute to dragondrop's container if you want to build your own set up.&#x20;

Our recommended approach:

1\) Define a [Cloud Run Job](https://cloud.google.com/run/docs/create-jobs) that hosts the dragondrop engine and supports all needed [environment variables](../environment-variables.md).

2\) Define an HTTPS endpoint that triggers the Cloud Run Job from 1) when a POST request is sent to it.

3\) Provide the API endpoint to your dragondrop [job definition](../../getting-started/jobs/creating-a-job.md). Done!
