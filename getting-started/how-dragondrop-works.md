---
description: Scan, recommend, import, and repeat.
---

# How dragondrop Works

### Structure of Usage

The core of dragondrop usage is a [Job](jobs/what-is-a-job.md). A Job references a single, uniquely configured, instance of the dragondrop container hosted within your public cloud environment.

Jobs are triggered either on a user-specified, dragondrop-managed Chron Schedule, or triggered manually through the dragondrop web application. Each time a Job runs, it will search for resources in your cloud environment that are outside of Terraform control, and if any are present, will open a Pull Request in your Version Control System with the code needed to import those resources into Terraform Control.

### Steps in Job Execution

Each dragondrop Job performs the following steps:

1\) Scan your existing cloud infrastructure environment

2\) Pull in your existing Terraform workspace state files from your remote state backend

3\) Identify cloud resources currently outside of Terraform control.

4\) Using machine learning, match new resources to the workspace to which they should likely belong.

5\) Generate the Terraform code and state migration statements needed to import the identified resources, by workspace.

6\) Open a pull request within your Version Control System (VCS) with the recommended changes, as well as a visual summary of the out-of-Terraform resources.

7\) Developer makes final approval, `plan` and `apply` recommend changes. All changes to your code base require developer approval.
