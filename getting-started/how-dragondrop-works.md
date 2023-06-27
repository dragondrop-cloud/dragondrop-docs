---
description: Scan, recommend, import, and repeat.
---

# How dragondrop Works

### Structure of Usage

The core of dragondrop usage is a [Job](jobs/what-is-a-job.md). A Job references a single, uniquely configured, instance of the cloud-concierge container hosted within your public cloud environment.

Jobs are triggered either on a user-specified, dragondrop-managed Chron Schedule, or triggered manually through the dragondrop web application. Each time a Job runs, it will search for resources in your cloud environment that are outside of Terraform control, and if any are present, will open a Pull Request in your Version Control System with the code needed to import those resources into Terraform Control.

<figure><img src="../.gitbook/assets/dragondrop architecture.png" alt=""><figcaption></figcaption></figure>

### Steps in Job Execution

These steps exactly match a developer's workflow when using [cloud-concierge](https://docs.cloudconcierge.io/how-it-works) in isolation:&#x20;

1\) cloud-concierge hosted in your cloud clones a Version Control repository of your choice, creates a representation of your designated cloud environment subset in Terraform, and pulls down the current state of Terraform by downloading remote state files. All data is stored ephemerally in a volume attached to the cloud-concierge container instance.

2\) Identify drift within resources managed by Terraform and new resources outside of Terraform control to codify.

3\) Identify the IAM accounts that made these changes to your cloud environment outside of your Terraform workflow.

4\) Run cost estimation and static security analysis over the Terraform files representing the current cloud environment state.

5\) Aggregrate results from previous steps and output via a Pull Request.
