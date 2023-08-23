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

### Version Control System (VCS) Env Vars&#x20;

`CONCIERGE_VCSTOKEN`

* **Description**: Personal access token for the VCS provider specified. Allows the containerized executable to interact with the VCS provider to open a pull request containing new resources and needed migrations.
  * For GitHub, should only be provided "Repo" permissions.
* **Example**: "ghp\_my-github-access-token"

### Terraform Cloud Env Vars  (if selected as your state backend)

`CONCIERGE_TERRAFORMCLOUDTOKEN`

* **Description**: Terraform cloud team token for accessing remote workspaces.
  * Should be a Terraform Cloud Team Token.
* **Example**: "my-tf-cloud-team token"
