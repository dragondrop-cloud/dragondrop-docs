---
description: A job is the core unit of how dragondrop is consumed, but what is it?
---

# What is a Job?

A Job is a single instance of the dragondrop container deployed within your cloud environment. During execution, the dragondrop container will scan your cloud environment and output identified, relevant results via a Pull Request into your Version Control System of choice.

Given that a Job has been purchased and configured, you can do the following:

* Execute the Job on a Chron Schedule or via an ad-hoc trigger through the [dragondrop web app](https://app.dragondrop.cloud) an unlimited number of times (we recommend triggering a job once a day).
* Scan and cover an unlimited area of your cloud environment with the job, as specified via  [environment variables](../../deploying-to-your-cloud/environment-variables.md) (we don't recommend scanning everything with one Job due to knowledge concentration and Pull Request verbosity, but you can if desired).
* Output results to a single code repository via a Pull Request.

