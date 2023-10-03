---
description: >-
  Because no sensitive data touches dragondrop servers, sensitive job
  parameterization occurs through environment variables attached to the compute
  running the dragondrop container.
---

# Environment Variables

## Resources

* All non-sensitive variables are specified via the dragondrop user interface for cloud-concierge job management.
* The dragondrop management platform offers a client-side environment variable validator to quickly check whether your environment variables are formatted correctly. This can be found [here](https://app.dragondrop.cloud/env-var-validator).

## Variable Descriptions

### Terraform Cloud Env Vars  (if selected as your state backend)

`CONCIERGE_TERRAFORMCLOUDTOKEN`

* **Description**: Terraform cloud team token for accessing remote workspaces.
  * Should be a Terraform Cloud Team Token.
* **Example**: "my-tf-cloud-team token"
