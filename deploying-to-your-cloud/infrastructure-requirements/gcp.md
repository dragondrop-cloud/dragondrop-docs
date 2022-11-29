---
description: >-
  Learn about our recommended infrastructure set up for deployments to Google
  Cloud Platform (GCP).
---

# GCP

Google Cloud Platform (GCP) makes it easy for you to provide serverless compute to dragondrop's container.

1\) Define a [Cloud Run Job](https://cloud.google.com/run/docs/create-jobs) that hosts the dragondrop engine.

2\) Define an HTTPS endpoint that triggers the Cloud Run Job from 1) when a POST request is sent to it.

3\) Provide the API endpoint to your dragondrop [job definition](../../getting-started/creating-a-job.md). Done!

## Terraform Module

Don't want to re-invent the wheel? Use our [Terraform Module](https://registry.terraform.io/modules/dragondrop-cloud/dragondrop-compute/google/latest) to host dragondrop within your cloud.

It creates a Cloud Run instance with a new service principal that can only update and invoke Cloud Run Jobs. The cloud run instance uses our open-sourced [Flask API service](https://github.com/dragondrop-cloud/cloud-run-job-http-trigger) container.

Unfortunately, we are awaiting Terraform support for Cloud Run Jobs within the GCP provider, but will cut a new release of the module as soon as possible.
